<h1 align="center">Urban Flood Prediction</h1>

<h2 align="center">Table of Contents</h2>

<ol class="toc" role="list">
    <li>
      <a href="#Abstract">
        <span class="title">Abstract</span>
      </a>
    </li>
    <li>
      <a href="#List of Tables">
        <span class="title">List of Tables</span>
      </a>
    </li>
    <li>
      <a href="#List of Figures">
        <span class="title">List of Figures</span>
      </a>
    </li>
    <li>
      <a href="#Introduction">
        <span class="title">Introduction</span>
      </a>
    </li>
    <li>
      <a href="#Methods">
        <span class="title">Methods</span>
      </a>
    </li>
    <ol class="toc" role="list">
      <li>
        <a href="#Study Area">
          <span class="title">Study Area</span>
        </a>
      </li>
      <li>
        <a href="#Data Sources and Processing">
          <span class="title">Data Sources and Processing</span>
        </a>
      </li>
      <li>
        <a href="#Flooding Inventory Data">
          <span class="title">Flooding Inventory Data</span>
        </a>
      </li>
    </ol>
    <li>
      <a href="#Results">
        <span class="title">Results</span>
      </a>
    </li>
    <li>
      <a href="#Discussion">
        <span class="title">Discussion</span>
      </a>
    </li>
    <li>
      <a href="#Conclusion">
        <span class="title">Conclusion</span>
      </a>
    </li>
    <li>
      <a href="#Acknowledgments">
        <span class="title">Acknowledgments</span>
      </a>
    </li>
    <li>
      <a href="#Data Access">
        <span class="title">Data Access</span>
      </a>
    </li>
    <li>
      <a href="#References">
        <span class="title">References</span>
      </a>
    </li>
</ol>


<h2 id = "Abstract">Abstract</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>

<h2 id = "List of Tables">List of Tables</h2>
<ol>
    <li>
      <a href="#Table 1">
        <span class="title">Table 1. Data Inputs</span>
      </a>
    </li>
</ol>

<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>

<h2 id = "List of Figures">List of Figures</h2>
<ol>
    <li>
      <a href="#Figure 1">
        <span class="title">Figure 1: Weather Sensor Locations in Pinellas County</span>
      </a>
    </li>
</ol>

<h2 id = "Introduction">Introduction</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>

<h2 id = "Methods">Methods</h2>

<h3 id = "Data Sources and Processing">Data Sources and Processing</h3>

<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The inputs into the CNN from various flood drivers and it's sources are listed in <a href="#Table 1">Table 1</a>.
</p>

<table id = "Table 1">
  <caption>Table 1. Data Inputs</caption>
  <thead>
    <tr>
      <th>Data</th>
      <th>Format</th>
      <th>Resolution</th>
      <th>Period</th>
      <th>Source</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Elevation</td>
      <td>Raster</td>
      <td>unk, I think 0.5-1 m, have to check point spacing</td>
      <td>2018</td>
      <td><a href="https://rockyweb.usgs.gov/vdelivery/Datasets/Staged/Elevation/LPC/Projects/FL_Peninsular_2018_D18/FL_Peninsular_Pinellas_2018/LAZ/" target="_blank">USGS</a></td>
      <td><a href="https://github.com/colarussoa/urban_flood_prediction/blob/main/Data/download%20LAS%20files.ipynb" target="_blank">See download LAS files.ipynb</a> Note: a DSM will be generated from the LAS following this procedure: <b>link to code snippet</b></td>
    </tr>
    <tr>
      <td>FDOT Aerial Imageries (w/ CIR band)</td>
      <td>Raster</td>
      <td>unk, I think 0.5 m</td>
      <td>2023</td>
      <td><a href="https://rockyweb.usgs.gov/vdelivery/Datasets/Staged/Elevation/LPC/Projects/FL_Peninsular_2018_D18/FL_Peninsular_Pinellas_2018/LAZ/" target="_blank">USGS</a></td>
      <td><a href="https://github.com/colarussoa/urban_flood_prediction/blob/main/Data/download%20LAS%20files.ipynb" target="_blank">See download LAS files.ipynb</a></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Landcover</td>
      <td>Raster</td>
      <td>unk, I think 0.5 m</td>
      <td>2023</td>
      <td><a href="https://coastalimagery.blob.core.windows.net/ccap-landcover/CCAP_bulk_download/High_Resolution_Land_Cover/Phase_2_Expanded_Categories/Land_Cover_post_2023/fl_tampa_2021_ccapv2_hires_landcover_20230512.zip" target="_blank">NOAA CONUS</a></td>
      <td>Will have to use USGS, I think. NOAA has restriction; This parameter can be inverted to increase accuracy. There's an associated confidence</td>
    </tr>
    <tr>
      <td>FDOT Aerial Imageries (w/ CIR band)</td>
      <td>Raster</td>
      <td>unk, I think 0.5 m</td>
      <td>2023</td>
      <td><a href="https://rockyweb.usgs.gov/vdelivery/Datasets/Staged/Elevation/LPC/Projects/FL_Peninsular_2018_D18/FL_Peninsular_Pinellas_2018/LAZ/" target="_blank">USGS</a></td>
      <td><a href="https://github.com/colarussoa/urban_flood_prediction/blob/main/Data/download%20LAS%20files.ipynb" target="_blank">See download LAS files.ipynb</a></td>
    </tr>
    <tr>
      <td>FDOT Aerial Imageries (w/ CIR band)</td>
      <td>Raster</td>
      <td>unk, I think 0.5 m</td>
      <td>2023</td>
      <td><a href="https://rockyweb.usgs.gov/vdelivery/Datasets/Staged/Elevation/LPC/Projects/FL_Peninsular_2018_D18/FL_Peninsular_Pinellas_2018/LAZ/" target="_blank">USGS</a></td>
      <td><a href="https://github.com/colarussoa/urban_flood_prediction/blob/main/Data/download%20LAS%20files.ipynb" target="_blank">See download LAS files.ipynb</a></td>
    </tr>
  </tfoot>
</table>

<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Rainfall data was collected by a sensor network installed by USF using the Ambient Weather Network (AWN) and open-source data from WeatherSTEM <a>Figure 1</a>
</p>

<figure>
    <img id="Figure 1" src="./figures/Figure_x_Weather Sensor Locations in Pinellas County.png" alt="Figure 1: Weather Sensor Locations in Pinellas County">
    <figcaption>Figure 1: Weather Sensor Locations in Pinellas County</figcaption>
</figure>


<h2 id = "Results">Results</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>

<h2 id = "Discussion">Discussion</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>

<h2 id = "Conclusion">Conclusion</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>

<h2 id = "Conclusion">Conclusion</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>

<h2 id = "Data Access">Data Access</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Data is stored <a href="https://github.com/colarussoa/urban_flood_prediction/tree/main/Data">in this GitHub Repository</a> or through <a href="https://usf.app.box.com/folder/337637864831">Box</a>. Information on how to download the data thorugh APIs, WMS, and Endpoints is available under <a>Notebooks/Download_Data in this Github repository</a>
</p>

<h2 id = "References">References</h2>
<p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Lorem Ipsum
</p>
