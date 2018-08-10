<template>
  <div id="app">
    <div id="view1"></div>
    <!--<router-view/>-->
  </div>
</template>

<script>

import * as neurobrain from 'neurobrain';

export default {
  name: 'App',
  mounted() {
    const viewer = new neurobrain.Viewer('foo');
    window.viewer = viewer;
    console.log('initialized viewer');

    const view1 = new neurobrain.View('view1');
    window.view = view1;
    console.log('initialized view');


    const file = 'https://cdn.rawgit.com/FNNDSC/data/master/nifti/adi_brain/adi_brain.nii.gz';
    viewer.addView(view1);
    console.log('added view');
    viewer.addLayer(file, view1);
    console.log('added layer');
  },
};

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#view1 {
  width: 500px;
  height: 500px;
}
</style>
