# 1. Load library
library(ggplot2)
library(readr)

# 2. Load dataset
data <- read_csv("hybrid_energy_storage.csv")

# 3. Cek struktur data (opsional)
str(data)
head(data)

# 4. Visualisasi 1: Energy Stored dari waktu ke waktu
ggplot(data, aes(x = Time, y = Energy_Stored)) +
  geom_line(color = "steelblue") +
  labs(title = "Energy Stored Over Time", x = "Time", y = "Energy Stored (kWh)") +
  theme_minimal()

# 5. Visualisasi 2: Energy Used vs Energy Stored
ggplot(data, aes(x = Energy_Used, y = Energy_Stored)) +
  geom_point(alpha = 0.5, color = "darkgreen") +
  labs(title = "Energy Used vs. Energy Stored", x = "Energy Used (kWh)", y = "Energy Stored (kWh)") +
  theme_classic()

# 6. Visualisasi 3: Battery Temperature dari waktu ke waktu
ggplot(data, aes(x = Time, y = Battery_Temperature)) +
  geom_line(color = "firebrick") +
  labs(title = "Battery Temperature Over Time", x = "Time", y = "Temperature (°C)") +
  theme_light()
