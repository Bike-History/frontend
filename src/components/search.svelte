<!-- Script -->
<script>
  import IMagnifier from "./icons/i-magnifier.svelte";
  import { searchInput } from '../store.js';

  const searchInputChanged = (e) => {
    searchInput.update(() => e.target.value)
  };
</script>

<!-- DOM -->
<div class="search row a-c">
  <IMagnifier/>
  <input
    type="text"
    on:input={searchInputChanged}
    class="search__input"
    placeholder="Seach"
  />
</div>

<!-- Style -->
<style lang="scss">
	@import "./style/global.scss";

  .search {
    border: 1px solid $c-shaddow;
    border-radius: $br-md;
    padding: $space-sm $space-md;
    color: $c-primary-lightest;
    height: $font-lg;
    &__input {
      flex-grow: 1;
      color: $c-primary;
      font-size: $font-md;

      ::placeholder { /* Chrome, Firefox, Opera, Safari 10.1+ */
        color: $c-shaddow;
        opacity: 1; /* Firefox */
      }

      :-ms-input-placeholder { /* Internet Explorer 10-11 */
        color: $c-shaddow;
      }

      ::-ms-input-placeholder { /* Microsoft Edge */
        color: $c-shaddow;
      }
    }
  }
</style>