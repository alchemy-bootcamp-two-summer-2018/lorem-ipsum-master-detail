/<template>
    <div class="ipsums">
        <AddIpsum         
        :onAdd="handleAdd"
        />
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
// contains functionality for adding or editing ipsums

import ipsumApi from '../services/ipsumApi';
import IpsumList from './IpsumList';
import Ipsum from './Ipsum';
import AddIpsum from './AddIpsum';

export default {

  data() {
    return {
      ipsums: ipsumApi.getIpsums(),
      selectedIpsum: null,
      ipsum: {
        title: '',
        category: '',
        author: '',
        authorUrl: '',
        publishedOn: '',
        body: ''
      },
    };
  },
  components: {
    AddIpsum,
    IpsumList,
    Ipsum
  },
  methods: {
    handleSelect(ipsum){
      this.selectedIpsum = ipsum;
    },
    handleUpdate(updated) {
      const index = this.ipsums.findIndex(ipsum => {
        return ipsum.title === updated.title; //key?
      });
      if(index !== -1) {
        this.ipsums.splice(index, 1, updated);
        this.selectedIpsum = updated;
      }
    },
    handleAdd(ipsum) {
      this.ipsums.push(ipsum);
    }
  }
};

</script>

<style>
.ipsums {
  display:flex;
  flex-direction: column;
}

</style>
