## Experience

* **Rating-based** approaches are sensitive to **context-change** and **subjectivity**
* **Ontology-based** experiences are **context-aware** and can successfully handle **subjectivity**
	* **Cased-Based Reasoning (CBR)**:
		* Score for experience i: S<sub>i</sub> = recency<sub>i</sub> × sim<sub>i</sub> × sat<sub>i</sub>
		* recency<sub>i</sub>: recency factor
		* sim<sub>i</sub>: similarity factor (**context similarity** to the current demand)
		* sat<sub>i</sub>: satisfaction factor
	* **Gaussian Model (GM)**: 
		* Select the provider with the **highest satisfaction probability**

Comparison between CBR and GM (P<sub>CD</sub> = The change of context for service demand):
<p float="left">
	<img src="./pix/service-selection-performance.png" width="400" />
	<img src="./pix/service-selection-performance.png" width="400" />
</p>
