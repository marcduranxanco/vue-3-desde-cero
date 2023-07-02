<script>
    export default {
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
                };

                this.proyectos.push(proyecto);

                this.proyecto = "";
                this.tipo = "";
                this.urgente = false;
            },
            cambiarEstado (id) {
                this.proyectos[id].urgente = !this.proyectos[id].urgente
            }
        },
        computed: {
            numeroProyectos() {
                return this.proyectos.length
            }
        }
    }
</script>

<template>
    <div class="row">
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
                    <label class="form-check-label" for="exampleCheck1">Urgente</label>
                    <input v-model="urgente" type="checkbox" class="form-check-input">
                </div>
                <button type="submit" class="btn btn-primary">Guardar</button>
            </form>
        </div>
        <div class="col-12 col-md-8">
            <h3> Total de proyectos: {{ numeroProyectos }}</h3>
            <div class="table-responsive">
                <table class="table table-dark table-hover">
                    <thead>
                        <tr>
                            <th>#</th>
                            <th>Proyecto</th>
                            <th>Tipo</th>
                            <th>Urgente</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(proyecto, index) in proyectos" :key="index">
                            <td>{{ index+1 }}</td>
                            <td>{{ proyecto.proyecto}}</td>
                            <td>{{ proyecto.tipo}}</td>
                            <td @click="cambiarEstado(index)" :class="proyecto.urgente ? 'bg-success' : 'bg-danger'">
                                {{ proyecto.urgente ? 'Sí' : 'No' }}
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>