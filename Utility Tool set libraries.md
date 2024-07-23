# Utility libraries to read, parse and plot data for Data Exploration 

# 1:  Reading Data from website in csv format
   # -> Ways to read data from http

   # 1. pyfetch
      from pyodide.http import pyfetch
      resp = await pyfetch(url)
       if resp.status == 200:
           with open(filename, "wb") as f:
               f.write(await resp.bytes())
   
      df = pd.read_csv("FuelConsumption.csv")


      
# 2:  Plot Data from website in csv format
   # -> Ways to Plot data from http

   # 1. Hist()
   Shows histogram of all Data columns 
       df.hist()
       plt.show()
       ![histogram](https://github.com/user-attachments/assets/ede4b86d-49e0-4cf9-bc5e-47e7b29ad576)
       
   # 2. Scatter() 
   Shows scatter of Data wrt to x, y labels
        plt.scatter(df.FUELCONSUMPTION_COMB, df.CO2EMISSIONS,  color='#f62681')
        plt.xlabel("FUELCONSUMPTION_COMB")
        plt.ylabel("CO2EMISSIONS")
        plt.show()
        ![scatter](https://github.com/user-attachments/assets/162ca8dd-c6f7-4227-8493-02645282d475)
