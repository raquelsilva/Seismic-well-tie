# Seismic-well tie

In this repository you will find some tools that will help you to read and work with geophysical logs - like the ANP (Petroleum Agency of Brazil) well logs files (.las) - or work with analogical logs, in order to create a time-depth table to be imported to an interpretation software.

It is necessary to have the data to run the code. If you don't have any ANP data you can use any .las file. 

The time-depth table is a crucial item to start a good interpretation of seismic data. I have already worked interpreting that kind of data and frequently this would be a big challenge - to fit well logs with seismic data. The interpratation softwares have the advantage of the seismic data to helping the seismic-well tie proccess. However, my experience shows that it's necessary more interaction in this proccess. The solution I'm proposing is to use geological markers and a window above and below the markers to analyse the acoustic impedance and its response at the synthetic seismogram. The geologist/geophysicist can create as many markers as necessary in order to classify the logs according to significant changes in velocity or density. 

If you don't have a .las file, it's possible to digitize logs you have in an image or on a paper. I recommend the web app href="https://apps.automeris.io/wpd/">Web Plot Digitizer</a>. 

After digitizing you will notice that the data has uneven sampling interval. It can be a problem if you need, for instance, multiplying the velocity and density logs to create a acoustic impedance log. To solve this problem, I've created a code to resample the data in a sample interval that you decide or import from a .las data. You will find that code in the file href="https://github.com/raquelsilva/Seismic-well-tie/blob/master/Reamostrar-perfil-digitalizado.ipynb">Reamostrar-perfil-digitalizado.ipynb</a>.

Other import step needed before starting the interpretation of seismic lines is to integrate all the pieces of logs that you have in your .las files. For starting my studies in the master's degree I received from the ANP data of 9 wells. All the 9 well have the data divided in more than one file. Looking at the well reports I notice that it happens when during the acquisition the operation needs to be stopped for some reason. So, a new set of data is stored in a different file or different column. 

If you try to import the logs in an interpretation software it's possible that only part of the data will be indeed imported. I'm using the software OpendTect (OT) for interpreting my data now. During my master's I've used the software Petrel (PT). The OT, for instance, dowsn't allow me to import two logs that have the same name. So, to be able to import them, sometimes I needed to change the name of one of them. But, importing the log data with different names doesn't help during the seismic-well tie proccess because I can calculate the synthetic seismogram using only one of the segments. Because of this I've created the code href="https://www.anaconda.com">Inegrar-perfis.ipynb</a>. In that code you can import your data of .las files or your digitized file, integrate DT and RHOB logs and export them to a .txt file. The next step can be done in a txt editor. You need to copy the header of a .las file, update the information according to your data and save is as a new .las file. 


