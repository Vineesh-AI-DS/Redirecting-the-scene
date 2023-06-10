# Redirecting-the-scene

## Aim:
To Redirect the scene in the unity engine.


## Algorithm:
## Step 1:
Open the unity engine.

## Step 2:
Create a new plane, a cube and a sphere and give them color.

## Step 3:
Create a tag for the Sphere and Make the sphere and cube as a Rigidbodies and Make the sphere use Gravity.

## Step 4:
Create the C# script file in the Assets and write the Coding for the Redirecting.

## Step 5:
Next Create a another new scene named as Level2.

## Step 6:
In File->Build settings and drop the both Level1 and Level2 scene in the Scenes in build setting.

## Step 7:
Click the Build and run button in the Build settings and run the scene.

## Step 8:
The Sphere after touching the cube it will disappeared and Press the key [R] the redircting to the new scene that is page2.

## Program:
```
Developed by: Vineesh.M
Register Number: 212221230122
```
```cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine.SceneManagement;
using UnityEngine;

public class cube : MonoBehaviour
{
    Rigidbody rb;
    public GameObject WinText; // Text Box - to display win
    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    // Update is called once per frame
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.R))
        {
            SceneManager.LoadScene("Level2");
        }        
    }
    public void OnMouseDown()
    {
        Destroy(gameObject);
    }
    private void OnCollisionEnter(Collision collision)
    {
        if(collision.gameObject.tag == "sphere")
        {
            Destroy(collision.gameObject);
            WinText.SetActive(true);
        }
    }
}
```

## Output:
## Scene 1:
## Sphere before hitting cube:
## Sphere after hitting cube:
## Redirected scene:
## Result:
Thus, redirecting the scene is successfully execcuted in the unity engine.
