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
            }
        }
    }
</script>

<template>
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

    <hr>

    <div class="table-responsive">
        <table class="table table-dark">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Proyecto</th>
                    <th>Tipo</th>
                    <th>Urgente</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>1</td>
                    <td>Laravel App</td>
                    <td>Laravel</td>
                    <td class="bg-success">True</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>