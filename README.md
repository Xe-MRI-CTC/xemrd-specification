# Xe MRD Specifications
-----------
## GX Pipeline File Naming
***1.*** **Sequence**: Proton <br>
> **File Name**: "subjectID_proton" <br>
> **Extenstion**: ".h5" <br>
> **Notes**: <br>

***2.*** **Sequence**: Calibration <br>
> **File Name**: "subjectID_calibration" <br>
> **Extenstion**: ".h5" <br>
> **Notes**: <br>

***3.*** **Sequence**: Dixon <br>
> **File Name**: "subjectID_dixon" <br>
> **Extenstion**: ".h5" <br>
> **Notes**: <br>

---------------
## GX Pipeline Variables
***1.*** **Variable**: `scan_date` <br>
> **Description**: scan date <br>
> **Units**: YYYY-MM-DD <br>
> **MRD Location Field**: `ismrmrdHeader.studyInformation.studyDate`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: Previous location was ismrmrdHeader.measurementInformation.scandate. Scandate is not a member of the ismrmrdHeader class in ismrmrd python package <br>

***2.*** **Variable**: `subject_id` <br>
> **Description**: subject ID <br>
> **Units**: string <br>
> **MRD Location Field**: `ismrmrdHeader.subjectInformation.patientID`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: If unavailable from raw data, you do not need to write the field <br>

***3.*** **Variable**: `system_vendor` <br>
> **Description**: MRI system vendor (e.g. 'Siemens') <br>
> **Units**: string <br>
> **MRD Location Field**: `ismrmrdHeader.acquisitionSystemInformation.systemVendor`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**:<br>

***4.*** **Variable**: `institution` <br>
> **Description**: institution (e.g. 'University of Iowa') <br>
> **Units**: string <br>
> **MRD Location Field**: `ismrmrdHeader.acquisitionSystemInformation.institutionName`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***5.*** **Variable**: `field_strength` <br>
> **Description**: scanner field strength <br>
> **Units**: Tesla <br>
> **MRD Location Field**: `ismrmrdHeader.acquisitionSystemInformation.systemFieldStrength_T`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***6.*** **Variable**: `te90` <br>
> **Description**: echo time <br>
> **Units**: ms <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.TE`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***7.*** **Variable**: `tr_proton` <br>
> **Description**: time between proton excitations <br>
> **Units**: ms <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.TR[0]`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: No <br>
> **Dixon**: No <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***8.*** **Variable**: `tr_gas` <br>
> **Description**: Calibration sequence: time between gas excitations. Dixon sequence: time from gas to dissolved excitation <br>
> **Units**: ms <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.TR[0]`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**: Note that in interleaved sequences, this can be different from tr_dis <br>

***9.*** **Variable**: `tr_dis` <br>
> **Description**: Calibration sequence: time between dissolved excitations. Dixon sequence: time from dissolved to gas excitation <br>
> **Units**: ms <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.TR[1]`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**: Note that in interleaved sequences, this can be different from tr_gas <br>

***10.*** **Variable**: `flip_angle_proton` <br>
> **Description**: proton flip angle <br>
> **Units**: degrees <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.flipAngle_deg[0]`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: No <br>
> **Dixon**: No <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***11.*** **Variable**: `flip_angle_gas` <br>
> **Description**: gas phase flip angle <br>
> **Units**: degrees <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.flipAngle_deg[0]`<br>
> **MRD Name/Label**: N/A<br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**:<br>

***12.*** **Variable**: `flip_angle_dis` <br>
> **Description**: dissolved phase flip angle <br>
> **Units**: degrees <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.flipAngle_deg[1]`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**: <br>

***13.*** **Variable**: `ramp_time` <br>
> **Description**: ramp time <br>
> **Units**: us <br>
> **MRD Location Field**: `ismrmrdHeader.encoding[0].trajectoryDescription.userParameterLong` <br>
> **MRD Name/Label**: `ramp_time` <br>
> **Calibration**: No <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: This is a user-defined variable that is not in userParameterLong by default. Each index, has a 'name' and 'value'. We previously specified location by index number, changed to specifying by variable name <br>

***14.*** **Variable**: `sample_time` <br>
> **Description**: time between digitized samples (AKA dwell time) <br>
> **Units**: us <br>
> **MRD Location Field**: `AcquisitionHeader.sample_time_us`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: Previous location was ismrmrdHeader.encoding[0].trajectoryDescription.userParameterDouble[0]. Note that this parameter has a value for each FID acquisition. <br>

***15.*** **Variable**: `prep_pulses` <br>
> **Description**: Indicates the use of prep pulses prior to data acquisition, e.g. in order to destroy downstream magnetization <br>
> **Units**: boolean <br>
> **MRD Location Field**: `ismrmrdHeader.sequenceParameters.prep_pulses` <br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: TRUE = prep pulses were used; FALSE = prep pulses were not used <br>

***16.*** **Variable**: `xe_center_frequency` <br>
> **Description**: center frequency of 129Xe in the gas phase <br>
> **Units**: Hz <br>
> **MRD Location Field**: `ismrmrdHeader.userParameters.userParameterLong`<br>
> **MRD Name/Label**: `xe_center_frequency` <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**: This is a user-defined variable that is not in userParameterLong by default. Previous location was ismrmrdHeader.encoding[0].trajectoryDescription.userParameterDouble[2] <br>

***17.*** **Variable**: `xe_dissolved_offset_frequency` <br>
> **Description**: dissolved phase frequency minus center frequency <br>
> **Units**: Hz <br>
> **MRD Location Field**: `ismrmrdHeader.userParameters.userParameterLong`<br>
> **MRD Name/Label**: `xe_dissolved_offset_frequency` <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**: This is a user-defined variable that is not in userParameterLong by default. Previous location was ismrmrdHeader.encoding[0].trajectoryDescription.userParameterDouble[3]. <br>

***18.*** **Variable**: `matrix_size_z` <br>
> **Description**: size of matrix in z dimension<br>
> **Units**: unitless integer <br>
> **MRD Location Field**: `ismrmrdHeader.encoding[0].reconSpace.matrixSize.z`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: No <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***19.*** **Variable**: `orientation` <br>
> **Description**: orientation of reconsructed image <br>
> **Units**: string ("coronal", "transverse", or "axial") <br>
> **MRD Location Field**: `ismrmrdHeader.userParameters.userParameterString`<br>
> **MRD Name/Label**: `orientation` <br>
> **Calibration**: No <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**:<br>

***20.*** **Variable**: `fov[0]` <br>
> **Description**: field of view x dimension <br>
> **Units**: mm <br>
> **MRD Location Field**: `ismrmrdHeader.encoding[0].reconSpace.fieldOfView_mm.x`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***21.*** **Variable**: `fov[1]` <br>
> **Description**: field of view y dimension <br>
> **Units**: mm <br>
> **MRD Location Field**: `ismrmrdHeader.encoding[0].reconSpace.fieldOfView_mm.y`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***22.*** **Variable**: `fov[2]` <br>
> **Description**: field of view z dimension <br>
> **Units**: mm <br>
> **MRD Location Field**: `ismrmrdHeader.encoding[0].reconSpace.fieldOfView_mm.z`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: <br>

***23.*** **Variable**: `traj_gas`/`traj_dis`/`traj_proton` <br>
> **Description**: k-space trajectory for gas, dissolved, or proton scan <br>
> **Units**: array-like, from -0.5 to 0.5 k-max <br>
> **MRD Location Field**: `Acquisition.traj`<br>
> **MRD Name/Label**: N/A <br>
> **Calibration**: No <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: Note that this parameter has a value for each FID acquisition <br>

***24.*** **Variable**: `contrast_labels` <br>
> **Description**: denotes whether an FID acquisition corresponds to proton, Xe gas phase or Xe dissolved phase excitation <br>
> **Units**: unitless integer <br>
> **MRD Location Field**: `AcquisitionHeader.idx.contrast`<br>
> **MRD Name/Label**: proton = 0, gas = 1, dissolved = 2 <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: Yes <br>
> **Notes**: Note that this parameter has a value for each FID acquisition <br>

***25.*** **Variable**: `bonus_spectra_labels` <br>
> **Description**: denotes whether an FID acquisition is part of bonus spectra or not <br>
> **Units**: unitless integer <br>
> **MRD Location Field**: `AcquisitionHeader.measurement_uid`<br>
> **MRD Name/Label**: not bonus spectra acquisition = 0, bonus spectra acquisition = 1 <br>
> **Calibration**: Yes <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**: Note that this parameter has a value for each FID acquisition <br>

***26.*** **Variable**: `set_labels` <br>
> **Description**: denotes the echo number to which a FID belongs for multi-echo sequences <br>
> **Units**: unitless integer <br>
> **MRD Location Field**: `AcquisitionHeader.idx.set`<br>
> **MRD Name/Label**: first echo = 1, second echo = 2, etc <br>
> **Calibration**: No <br>
> **Dixon**: Yes <br>
> **Proton**: No <br>
> **Notes**: Note that this parameter has a value for each FID acquisition <br>

