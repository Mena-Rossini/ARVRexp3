# Ex3---Hurdle-Game-2D

## AIM :

To develop a 2D game using C# program in unity .

## ALGORITHM :

### STEP 1 :

Create a 2D project in unity.

### STEP 2 :

Add player,hurdles,coins,track in the frame and add the valid collider2D component.

### STEP 3 :

Click Assets->Create-># Script.

### STEP 4 :

create player.cs and coinmanger script and add c# code.

### STEP 5 :

Click canvas->Gamemanager->add Score and value.

### STEP 6 :

Drag the script to player and coin.

### STEP 7 :

Run the scene and display the output.

## PROGRAM :

### DEVELOPED BY :Onteddu Sirisha
### REG NO : 212222230103

### player.cs :
```
using UnityEngine;
using System.Collections;
using System.Collections.Generic;

public class player : MonoBehaviour
{
    public float speed, jumpforce;
    private Rigidbody2D rb;
    public Score cc;
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        rb=GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        float moveinp=Input.GetAxisRaw("Horizontal");
        transform.position=new Vector3(moveinp,0,0)*speed*Time.deltaTime;
        if(Input.GetKeyDown(KeyCode.Space) && Mathf.Abs(rb.linearVelocity.y)<0.001f)
        {
            rb.AddForce(new Vector2(0,jumpforce),ForceMode2D.Impulse);
        }
    }
    private void OnTriggerEnter2D(Collider2D other)
    {
        if(other.CompareTag("Destroy"))
        {
            cc.coincount++;
            Destroy(other.gameObject);
        }
    }
}

```
### CoinManager.cs :
```
using UnityEngine;
using System.Collections;
using System.Collections.Generic;
using UnityEngine.UI;
public class Score : MonoBehaviour
{
    public int coincount;
    public Text Value;
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        Value.text=coincount.ToString();
    }
}

```



## OUTPUT:
![image 1](https://github.com/user-attachments/assets/cec02145-e83c-465d-909e-ae8639227355)

![image 2](https://github.com/user-attachments/assets/ebb0c6b7-0d94-4ba9-ab24-ccd348b7a607)


## RESULT :

Thus a 2D game using C# program in unity is developed successfully.
