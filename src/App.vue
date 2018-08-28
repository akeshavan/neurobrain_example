<template>
  <div id="app">

    <div class="views">
      <div id="view1"></div>
      <div class="miniviews">
        <div id="view2"></div>
        <div id="view3"></div>
      </div>
    </div>
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

    const view1 = new neurobrain.View('view1', 'axial');
    window.view1 = view1;
    console.log('initialized view');

    const view2 = new neurobrain.View('view2', 'sagittal');
    window.view2 = view2;
    console.log('initialized view2');

    const view3 = new neurobrain.View('view3', 'coronal');
    window.view3 = view3;

    const file = 'https://dxugxjm290185.cloudfront.net/hbn/sub-NDARKH741PL8/anat/sub-NDARKH741PL8_T1w.nii.gz?dl=0'; 
    // 'https://cdn.rawgit.com/FNNDSC/data/master/nifti/adi_brain/adi_brain.nii.gz';
    viewer.addView(view1);
    viewer.addView(view2);
    viewer.addView(view3);
    console.log('added view 1,2,3');
    viewer.addData(file, 'base_image')
      .then((series) => {
        viewer.addLayer(series, 'view1');
        viewer.addLayer(series, 'view2');
        viewer.addLayer(series, 'view3');
        console.log('added layer 1,2,3');
      });

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

.views {
  display: flex;
}

.miniviews {
  display: block;
}

#view1 {
  width: 500px;
  height: 500px;
  display: inherit;
}

#view2 {
  width: 250px;
  height: 250px;
  display: inherit;
}

#view3 {
  width: 250px;
  height: 250px;
  display: inherit;
}
</style>
