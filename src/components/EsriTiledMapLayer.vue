<script>
  import { tiledMapLayer as TiledMapLayer } from 'esri-leaflet';
  export default {
    name: 'EsriTiledMapLayer',
    props: ['url'],
    render(h) { return; },
    mounted() {
      const leafletElement = this.$leafletElement = this.createLeafletElement()
    },
    methods: {
      createLeafletElement() {
        const { ...options } = this.$props;
        return new TiledMapLayer(options);
      },
      parentMounted(parent) {
        const map = parent.$leafletElement;
        this.$leafletElement.addTo(map);
      }
    }
  };
</script>
