<template>
    <div>
        <div class="row">
            <div class="col-6 my-2">
                <h3> Total de proyectos: {{ numeroProyectos }}</h3>
            </div>
            <div class="col-6 text-end">
                <button class="btn btn-warning" @click="limpiarData()">Limpiar Proyectos</button>
            </div>
        </div>

        <div class="table-responsive">
            <table class="table table-dark table-hover">
                <thead>
                    <tr>
                        <th>#</th>
                        <th>Proyecto</th>
                        <th>Tipo</th>
                        <th>Urgente</th>
                        <th>Completado</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(proyecto, index) in proyectos" :key="index">
                        <td>{{ index+1 }}</td>
                        <td>{{ proyecto.proyecto}}</td>
                        <td>{{ proyecto.tipo}}</td>
                        <td @click="cambiarEstado(proyecto, 'urgente')" :class="proyecto.urgente ? 'bg-success' : 'bg-danger'">
                            {{ proyecto.urgente ? 'Sí' : 'No' }}
                        </td>
                        <td @click="cambiarEstado(proyecto, 'completado')" :class="proyecto.completado ? 'bg-success' : 'bg-danger'">
                            {{ proyecto.completado ? 'Completo' : 'Incompleto' }}
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
export default {
    props: ["numeroProyectos", "proyectos", "cambiarEstado", "limpiarData"]
}
</script>