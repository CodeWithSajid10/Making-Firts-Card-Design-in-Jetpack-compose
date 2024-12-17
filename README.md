// # Making-Firts-Card-Design-in-Jetpack-compose
//it's the first card made myself using Kotlin and Jetpack Compose 


package com.example.myfirtsapplication

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.*
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.Alignment
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.compose.ui.text.font.FontWeight
import com.example.myfirtsapplication.ui.theme.MyFirtsApplicationTheme
import androidx.compose.foundation.Image
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.ui.draw.clip
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.graphics.painter.Painter

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MyFirtsApplicationTheme {
                Scaffold(
                    modifier = Modifier
                        .fillMaxSize()
                        .background(Color.White)
                ) { innerPadding ->
                    // Pass the padding to your content
                    Test(
                        modifier = Modifier.padding(innerPadding).fillMaxSize()
                    )
                }
            }
        }
    }
}

@Preview
@Composable
fun Test(modifier: Modifier = Modifier) {
    Card(
        modifier = Modifier
            .fillMaxWidth()
            .padding(30.dp)
    ) {
        Column(
            modifier = modifier
                .fillMaxWidth()
                .padding(20.dp), // No background color applied
            verticalArrangement = Arrangement.Center,
            horizontalAlignment = Alignment.CenterHorizontally
        ){

            Text(
                text = "I'm Android Developer",
                color = Color.Black, // Uncommented color for text
                fontSize = 20.sp,
                fontWeight = FontWeight.Bold,
                style = MaterialTheme.typography.bodyMedium
            )
            // You can add your image here if needed
            Image(
                painter = painterResource(id = R.drawable.profile), // Replace with your image resource
                contentDescription = "Profile Picture",
                modifier = Modifier
                    .size(100.dp) // Set size for the image
                    .padding(bottom = 22.dp)
                    .clip(RoundedCornerShape(15.dp))// Optional padding below the image
            )
        }
    }
}
