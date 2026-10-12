def calculate_trip_cost(distance_km, fuel_efficiency, fuel_price):
    if distance_km < 0 or fuel_efficiency <= 0 or fuel_price < 0:
        raise ValueError("Invalid travel parameters")

    liters_needed = distance_km / fuel_efficiency
    total_cost = liters_needed * fuel_price

    return {
        "distance_km": distance_km,
        "fuel_liters": round(liters_needed, 2),
        "total_cost": round(total_cost, 2),
    }


if __name__ == "__main__":
    trip = calculate_trip_cost(250, 15, 1.75)
    print("Trip estimate:", trip)
