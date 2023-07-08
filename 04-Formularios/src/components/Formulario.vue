<script>
    import ProgressBar from './ProgressBar.vue';
    import TotalProyectos from './TotalProyectos.vue';

    export default {
        components: {
            ProgressBar,
            TotalProyectos
        },
        data: () => ({
            proyecto: "",
            tipo: "",
            urgente: false,
            proyectos: []
        }),
        methods: {
            registrarProyecto () {
                const proyecto = {
                    proyecto: this.proyecto,
                    tipo: this.tipo,
                    urgente: this.urgente,
                    completado: false
                };

                this.proyectos.push(proyecto);

                this.proyecto = "";
                this.tipo = "";
                this.urgente = false;
            },
            cambiarEstado (proyecto, campo) {
                proyecto[campo] = !proyecto[campo]
            }
        },
        computed: {
            numeroProyectos() {
                return this.proyectos.length
            },
            porcentaje() {
                let completados = 0
                this.proyectos.map(proyecto => {
                    if(proyecto.completado) {
                        completados++
                    }
                })

                return (completados * 100) / this.numeroProyectos || 0;
            },

        }
    }
</script>

<template>
    <div class="row">
        <div class="col-12 mb-4">
            <ProgressBar :porcentaje=porcentaje />
        </div>
        <div class="col-12 col-md-4">
            <form @submit.prevent="registrarProyecto">
                <div class="mb-3">
                    <label class="form-label">Proyecto</label>
                    <input v-model.trim="proyecto" type="text" class="form-control" required/>
                </div>

                <div class="mb-3">
                    <label class="form-label">Actividad</label>
                    <select v-model="tipo" class="form-select" required>
                        <option disabled selected value="">Seleccione un tipo...</option>
                        <option>Aplicación web con Vue.Js</option>
                        <option>Backend Service con Node.Js</option>
                        <option>App Movil con React Native</option>
                    </select>
                </div>

                <div class="mb-3">
                    <label class="form-check-label">Urgente</label>
                    <input v-model="urgente" type="checkbox" class="form-check-input">
                </div>

                <button type="submit" class="btn btn-primary">Guardar</button>
            </form>
        </div>
        <div class="col-12 col-md-8">
            <TotalProyectos :numeroProyectos=numeroProyectos :proyectos=proyectos :cambiarEstado=cambiarEstado />
        </div>
    </div>
</template>