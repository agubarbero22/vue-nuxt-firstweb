<template>
    <div>
        <v-container>
            <h1>Elija sólo los módulos que necesite</h1>
        </v-container>

        <v-container fluid>
            <v-row dense v-for="(card, index) in cards" :key="index" >
                <template v-for="n in 2">
                    <v-col :key="n">
                        <custom-card class="pa-2" :title="card.title" :subTitle="card.subtitle" :imgPath="card.imgPath"> </custom-card>
                    </v-col>
                    <v-responsive v-if="n === 2" :key="`width-${n}`" width="100%" ></v-responsive>
                </template>
            </v-row>
        </v-container>
    </div>
</template>

<script>
import CustomCard from '../components/CustomCard.vue'
export default {
  components: { CustomCard },
    data() {
        return {
            cards: [
                {
                    title: '+ACCOMODATION',
                    subtitle: 'Permite a los agentes de viajes reservar alojamiento en todo el mundo, eligiendo entre más de 1.500.000 propiedades, incluyendo hoteles, apartamentos y casas vacacionales.',
                    imgPath: 'accomodation.png'
                },
                {
                    title: '+AIR',
                    subtitle: 'Permite a los agentes realizar reservas aéreas en todo el mundo. La plataforma ofrece tarifas aéreas más baratas con opciones de pago local.',
                    imgPath: 'air.png'
                },
                {
                    title: '+CARS',
                    subtitle: 'Vehículos sin conductor disponibles para alquilar en más de 100 países con las principales empresas de alquiler a nivel mundial y ofrecemos disponibilidad instantántea a los mejores precios con la opción de reservar ahora y pagar después.',
                    imgPath: 'cars.png'
                },
                {
                    title: '+TRANSFERS',
                    subtitle: 'Con este módulo podrá reservar su traslado privado desde el aeropuerto al hotel y viceversa en todo el mundo con una amplia variedad de opciones disponibles a las mejores tarifas, con un procedimiento de reserva sencillo y proveedores detalladamente seleccionados.',
                    imgPath: 'transfers.png'
                },
                {
                    title: '+CRUISERS',
                    subtitle: 'Hemos hecho una selección de cruceros de las mejores líneas de cruceros del mundo. Con una cartera que abarca desde líneas de cruceros conterporáneas hasta ultra lujosas, ofrecemos a sus clientes la oportunidad de disfrutar la mejor experiencia en el mar.',
                    imgPath: 'cruisers.png'
                },
                {
                    title: '+SIGHTSEEING',
                    subtitle: 'Genere experiencias inolvidables para uss clientes. Elija entre miles de opcoines de atracciones y recomendaciones antes y durante su viaje para experimentar mejor lo que el destino tiene para ofrecer.',
                    imgPath: 'sightseeing.png'
                },
                {
                    title: '+PACKAGES',
                    subtitle: 'Los agentes de viajes y los opreadores turísticos tienen dificultades para hacer frente a los clientes con diversas necesidades mientras buscan paquetes de vacaciones. Esta oportunidad sentó las bases para que pueda crear paquetes vacacionales dinámicos adaptados a sus clientes.',
                    imgPath: 'packages.png'
                },
                {
                    title: '+ASSISTANCE',
                    subtitle: 'Con este módulo podrá comprar seguros de viaje en l´´inea con la seguridad financiera necesaria para disfrutar de un viaje sin problemas.',
                    imgPath: 'assistance.png'
                },
                
            ],
        }
    }
}
</script>

<style>
    h1{
        font-family: Open Sans;
        font-style: normal;
        font-weight: 600;
        font-size: 36px;
        line-height: 49px;
        /* identical to box height */
        text-align: center;
        letter-spacing: -0.04em;
        /* Dark */
        color: #ffffff;
    }
</style>