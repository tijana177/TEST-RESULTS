# TEST-RESULTS
1. Izraz: 2+2
   Očekivani rezultat: 4
   Dobijeni rezultat: 4
   Rezultat je tačan

2. Izraz: 5-4*3
   Očekivani rezultat: -7
   Dobijeni rezultat: -7
   Rezultat je tačan

3. Izraz: 10/0
   Očekivani rezultat: greška (dijeljenje nulom)
   Dobijeni rezultat: ERROR
   Rezultat je tačan. Program ispravno prikazuje grešku.

4. Izraz: 7.8+1.6-0.9
   Očekivani rezultat: 8.5
   Dobijeni rezultat: 8.499999
   Rezultat nije tačan. Postoji problem sa tačnošću decimalnih brojeva.

Metodu ToString treba preimenovati u toString kako bi pratila konvencije za Java nazive metoda.
Metoda Calculate ne obrađuje slučaj kada ulazni izraz ima zagrade jer ne prepoznaje zagrade.
Postoji problem sa tačnošću decimalnih brojeva. Program prikazuje neprecizne rezultate u određenim slučajevima.
Navedeni jedinični test pokriva samo osnovnu operaciju oduzimanja.

import org.junit.Test;
import static org.junit.Assert.assertEquals;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class CalculatorTest {

@Test
public void testCalculate() {
List<Float> numbers = new ArrayList<>(Arrays.asList(7.0f, 3.0f, 5.0f));
List<String> operations = new ArrayList<>(Arrays.asList("+", "*", "-"));

Calculator.Calculate(numbers, operations);
float actualResult = Calculator.finalResult;
float expectedResult = 22;

assertEquals(expectedResult, actualResult, 0.0001);
}
}
