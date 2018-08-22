/<template>
    <div class="ipsums">
        <IpsumList
        :ipsums="ipsums"
        :selected="selectedIpsum"
        :onSelect="handleSelect"
        />
        <Ipsum 
            :ipsum="selectedIpsum"
            :onUpdate="handleUpdate"
        />
    </div>
</template>

<script>
import ipsumApi from '../services/ipsumApi';
import IpsumList from './IpsumList';
import Ipsum from './Ipsum';

export default {
    
  data() {
    return {
      ipsums: ipsumApi.getIpsums(),
      selectedIpsum: null,
    };
  },
  components: {
    IpsumList,
    Ipsum
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
