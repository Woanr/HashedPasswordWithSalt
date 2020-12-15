using System;
using System.Security.Cryptography;
using System.Text;

public class HashedPasswordWithSalt
{
    public static string HashPassword(string password)
    {
        var combinedPassword = string.Concat(password, GetRandomSalt());
        var sha256 = new SHA256Managed();
        var bytes = UTF8Encoding.UTF8.GetBytes(combinedPassword);
        var hash = sha256.ComputeHash(bytes);
        return Convert.ToBase64String(hash);
    }

    public static string GetRandomSalt(Int32 size = 12)
    {
        var random = new RNGCryptoServiceProvider();
        var salt = new byte[size];
        random.GetBytes(salt);
        return Convert.ToBase64String(salt);
    }
}
