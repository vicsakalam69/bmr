# bmr
  
/**
 * Calculates the Basal Metabolic Rate (BMR) using the Harris-Benedict equation.
 * 
 * @param {string} gender - The gender of the person ('male' or 'female').
 * @param {number} weight - The weight of the person in kilograms.
 * @param {number} height - The height of the person in centimeters.
 * @param {number} age - The age of the person in years.
 * @returns {number} The calculated BMR value.
 */
function calculateBMR(gender, weight, height, age) {
  try {
    // Check if the gender is valid
    if (gender !== 'male' && gender !== 'female') {
      throw new Error('Invalid gender. Please provide "male" or "female".');
    }

    // Check if the weight, height, and age are valid numbers
    if (typeof weight !== 'number' || typeof height !== 'number' || typeof age !== 'number') {
      throw new Error('Invalid input. Please provide valid numbers for weight, height, and age.');
    }

    let bmr = 0;

    // Calculate BMR based on gender
    if (gender === 'male') {
      bmr = 88.362 + (13.397 * weight) + (4.799 * height) - (5.677 * age);
    } else if (gender === 'female') {
      bmr = 447.593 + (9.247 * weight) + (3.098 * height) - (4.330 * age);
    }

    return bmr;
  } catch (error) {
    // Log the error
    console.error('Error:', error.message);
    return null;
  }
}
