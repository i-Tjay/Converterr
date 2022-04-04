import SwiftUI

struct ContentView: View {
    @State private var input = 100.0
    @State private var inputUnit = "Meters"
    @State private var outPutUnit = "Kilometers"
    
    let units = ["Feet", "Kilometers", "Meters", "Miles", "Yards"]
    var result: String {
        let inputToMetersMultiplier: Double
        let meterToOutPutMultiplier: Double
        
        switch inputUnit {
            case "Feet":
            inputToMetersMultiplier = 0.3048
        case "Kilometers":
            inputToMetersMultiplier = 1000
        case "Miles":
            inputToMetersMultiplier = 1609.34
        case "Yards":
            inputToMetersMultiplier = 0.9144
        default: inputToMetersMultiplier = 1.0
        }
        
        switch outPutUnit {
        case "Feet":
            meterToOutPutMultiplier = 3.28084
    case "Kilometers":
            meterToOutPutMultiplier = 0.001
    case "Miles":
            meterToOutPutMultiplier = 0.00621371
    case "Yards":
            meterToOutPutMultiplier = 1.09361
    default:
            meterToOutPutMultiplier = 1.0
            
        }
        
        let inputInMeters = input * inputToMetersMultiplier
        let outPut = inputInMeters * meterToOutPutMultiplier
        
        let outPutString = outPut.formatted()
        return "\(outPutString) \(outPutUnit.lowercased())"
    }
    
    
        
        
    var body: some View {
        NavigationView {
            Form {
                Section {
                    TextField("Amount", value: $input, format: .number)
                        .keyboardType(.numberPad)
                } header: {
                    Text("Amount to Convert")
                }
                Picker("Convert from", selection: $inputUnit) {
                    ForEach(units, id: \.self) {
                        Text($0)
                            
                    }
                    
                }
                Picker("Convert to", selection: $outPutUnit) {
                    ForEach(units, id: \.self) {
                        Text($0)
                    }
            }
                Section {
                    Text (result)
                    
                } header: {
                    Text("Result")
                }
                .navigationTitle("Converter")
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

}
