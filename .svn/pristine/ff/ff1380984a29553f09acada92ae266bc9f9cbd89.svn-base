package com.bcsis.g3.utility.passwordDecryptor;

import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.util.Properties;
import java.util.ResourceBundle;

import org.jasypt.encryption.pbe.StandardPBEStringEncryptor;

import com.bcsis.base.crypto.SecureSimpleStringPBEConfig;

public class Main {
	private ResourceBundle resourceBundle;
	private static final String KEY_FILE_PATH_KEY = "KEY.FILE.PATH";
	private static final String IPS_ACHOPR_PASSWORD_ENCRYPTED_KEY = "IPS.ACHOPR.PASSWORD.ENCRYPTED.KEY";
	private static final String ENCRYPTION_KEY = "ENCRYPTION.KEY";
	private static final String ENCRYPTION_ALGO = "PBEWithSHA1AndDESede";
	private static final String STRING_OUTPUT_TYPE = "hexadecimal";

	public static void main(String[] args) {
		try {
			Main main = new Main();
			String encryptedPassword = main.getEncryptedPassword();
			StandardPBEStringEncryptor standardPBEStringEncryptor = new StandardPBEStringEncryptor();
			SecureSimpleStringPBEConfig secureSimpleStringPBEConfig = new SecureSimpleStringPBEConfig();
			secureSimpleStringPBEConfig.setAlgorithm(ENCRYPTION_ALGO);
			secureSimpleStringPBEConfig.setPassword(main.getKey());
			secureSimpleStringPBEConfig.setStringOutputType(STRING_OUTPUT_TYPE);
			standardPBEStringEncryptor.setConfig(secureSimpleStringPBEConfig);
			System.out.print(standardPBEStringEncryptor.decrypt(encryptedPassword));
		} catch (Exception e) {
			e.printStackTrace();
			System.exit(-1);
		}

	}

	private Main() {
		this.resourceBundle = ResourceBundle.getBundle("conf");
	}

	private ResourceBundle getResourceBundle() {
		return resourceBundle;
	}

	private String getKey() throws Exception {
		String key = this.getResourceBundle().getString(ENCRYPTION_KEY);
		return key;
	}

	private String getEncryptedPassword() throws Exception {
		String keyFilePath = this.getResourceBundle().getString(KEY_FILE_PATH_KEY);
		String encryptedPasswordKey = this.getResourceBundle().getString(IPS_ACHOPR_PASSWORD_ENCRYPTED_KEY);
		Properties properties = new Properties();
		FileInputStream fileInputStream = null;
		try {
			fileInputStream = new FileInputStream(new File(keyFilePath));
			properties.load(fileInputStream);
			String str = properties.getProperty(encryptedPasswordKey);
			str = str.substring(4, str.length());
			str = str.substring(0, str.length() - 1);
			return str;
		} catch (Exception e) {
			throw e;
		} finally {
			if (fileInputStream != null) {
				try {
					fileInputStream.close();
				} catch (IOException e) {
					throw e;
				}
			}
		}
	}
}
