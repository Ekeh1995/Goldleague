# Goldleague
repositories {

    mavenCentral()

}<application>
  <meta-data android:name="io.sentry.dsn" android:value="https://db955202efdc49639d24a3d31ac43ac4@o792606.ingest.sentry.io/5801085" />
</application>import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import java.lang.Exception;

import io.sentry.Sentry;

public class MyActivity extends AppCompatActivity {

  protected void onCreate(Bundle savedInstanceState) {

    super.onCreate(savedInstanceState);

    try {

      throw new Exception("This is a test.");

    } catch (Exception e) {

      Sentry.captureException(e);

    }

  }

}
