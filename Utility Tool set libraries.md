# Utility libraries to read, parse and plot data for Data Exploration 

# 1:  Reading Data from website in csv format
   # -> Ways to read data from http

   # 1.1. pyfetch
      from pyodide.http import pyfetch
      resp = await pyfetch(url)
       if resp.status == 200:
           with open(filename, "wb") as f:
               f.write(await resp.bytes())
   
      df = pd.read_csv("FuelConsumption.csv")


      
# 2:  Plot Data from website in csv format
   # -> Ways to Plot data from http

   # 2.1. Hist()
   Shows histogram of all Data columns 
   
       df.hist()
       plt.show()
       
   ![histogram](https://github.com/user-attachments/assets/ede4b86d-49e0-4cf9-bc5e-47e7b29ad576)
       
   # 2.2 Scatter() 
   Shows scatter of Data wrt to x, y labels
   
        plt.scatter(df.FUELCONSUMPTION_COMB, df.CO2EMISSIONS,  color='#f62681')
        plt.xlabel("FUELCONSUMPTION_COMB")
        plt.ylabel("CO2EMISSIONS")
        plt.show()
        
   ![scatter](https://github.com/user-attachments/assets/162ca8dd-c6f7-4227-8493-02645282d475)

# 3. Data Analysis 

   # 3.1 Data describe

      df.describe()
   # 3.2 Data output vaue count or co unt of lables in the output/target column 

   df.['CO2EMISSIONS'].value_counts()

      # output
      0.0    2843150
      1.0       4920
      Name: Class, dtype: int64


# 4 Data Visualisation
   # 4.1 Create a hist of all columns
      plt.clf()
      df.hist()
      plt.show()
      
      ![Datahist](https://github.com/user-attachments/assets/aba445d0-3c20-477c-abda-03af12d9a73d)

   # 4.2 Create a scatter plot with the two input columns and the output column
plt.scatter(df['column1'], df['column2'], c=df['column_out'])
![scatterof rev col](https://github.com/user-attachments/assets/fecde2a3-2df2-4329-8eef-cd1e7d83c455)
