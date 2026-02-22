using System;
using System.Security.Cryptography;

class Program
{
    static void Main()
    {
        string authCode = GenerateOtp(6);
        Console.WriteLine("Authentication Code: " + authCode);
    }

    static string GenerateOtp(int length)
    {
        const string digits = "0123456789";
        char[] result = new char[length];

        using (RandomNumberGenerator rng = RandomNumberGenerator.Create())
        {
            byte[] buffer = new byte[length];
            rng.GetBytes(buffer);

            for (int i = 0; i < length; i++)
            {
                result[i] = digits[buffer[i] % digits.Length];
            }
        }

        return new string(result);
    }
}
