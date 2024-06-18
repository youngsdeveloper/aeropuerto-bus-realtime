<template>
    
    <div class="timetable">
        <h2 class="subtitle is-5">Horarios Bus Murcia - Aeropuerto Corvera</h2>
        
        <table class="table is-striped is-bordered is-fullwidth">
            <thead>
            <tr>
                <th>Murcia</th>
                <th>Aeropuerto</th>
                <th>Murcia</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(time,index) in timetableMurciaAeropuerto" v-bind:key="index">
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

        <h2 class="subtitle is-5">Horarios Bus Cartagena - Aeropuerto Corvera</h2>
        <table class="table is-striped is-bordered is-fullwidth">
            <thead>
            <tr>
                <th>Cartagena</th>
                <th>Aeropuerto</th>
                <th>Cartagena</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(time,index) in timetableCartagenaAeropuerto" v-bind:key="index">
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

            timetableMurciaAeropuerto: [
                ["7:30","9:00","-"],
                ["-","10:00", "10:30"],
                ["10:30","11:00","-"],
                ["-","13:00","13:30"],
                ["13:30","14:00","-"],
                ["-","14:00","14:30"],
                ["15:00","15:30","-"],
                ["-","17:00","17:30"],
                ["18:00","18:30","-"],
                ["-","20:30","21:00"],
                ["21:00","21:30","-"],
                ["-","21:30","22:00"],


            ],

            timetableCartagenaAeropuerto: [
                ["-", "8:15", "9:00"],
                ["9:00", "9:45","-"],
                ["-", "11:00", "11:45"],
                ["12:15", "13:00", "-"],
                ["-", "15:30", "16:15"],
                ["16:15", "17:00", "-"],
                ["-", "18:30", "19:15"],
                ["19:15", "20:00", "-"],



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