<template>
    
    <div class="timetable">
        <h2 class="subtitle is-5">Horarios bus Murcia - Aeropuerto - Cartagena</h2>
        
        <table class="table is-striped is-bordered is-fullwidth">
            <thead>
            <tr>
                <th>Murcia</th>
                <th>Aeropuerto</th>
                <th>Cartagena</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(time,index) in timetableMurciaCartagena" v-bind:key="index">
                <td>
                {{ time[0] }}
                </td>
                <td>
                {{ time[1] }}
                </td>
                <td>
                {{ time[2] }}
                </td>
            </tr>
            </tbody>
        </table>

        <h2 class="subtitle is-5">Horarios bus Cartagena - Aeropuerto - Murcia</h2>
        <table class="table is-striped is-bordered is-fullwidth">
            <thead>
            <tr>
                <th>Cartagena</th>
                <th>Aeropuerto</th>
                <th>Murcia</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(time,index) in timetableCartagenaMurcia" v-bind:key="index">
                <td>
                {{ time[0] }}
                </td>
                <td>
                {{ time[1] }}
                </td>
                <td>
                {{ time[2] }}
                </td>
            </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    data(){
        return{

            timetableMurciaCartagena: [
                ["8:30","9:00 - 9:10", "9:55"],
                ["12:30","13:00 - 13:10", "13:55"],
                ["19:00","19:30 - 19:40", "20:25"]
            ],

            timetableCartagenaMurcia: [
                ["10:30","11:15 - 11:25", "11:55"],
                ["14:00","14:45 - 14:55", "15:25"],
                ["20:30","21:15 - 21:25", "21:55"]
            ]
        }
    }
}
</script>

<style scoped>

.timetable{
    text-align: center;
    padding: 20px 80px;
}

@media only screen and (max-width: 600px) {
  
    .timetable{
        padding: 20px 20px;
    }
}
</style>