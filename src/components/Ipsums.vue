/<template>

    <IpsumList
    :ipsums="ipsums"
    :selected="selectedIpsum"
    :onSelect="handleSelect"
    />

</template>

<script>
import ipsumApi from '../services/ipsumApi';
import IpsumList from './IpsumList';

export default {
    
  data() {
    return {
      ipsums: ipsumApi.getIpsums(),
      selectedIpsum: null,
    };
  },
  components: {
    IpsumList,
  },
  methods: {
    handleSelect(ipsum){
      this.selectedIpsum = ipsum;
    }
  }
};

</script>


<style>

</style>
