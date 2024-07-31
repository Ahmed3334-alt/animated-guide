hello
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class MOVEPlLAUER : MonoBehaviour
{
   
      public CharacterController controller;
   public int speed = 5;
   private bool isGraunded;
   public Transform Sphere;
   public LayerMask sloy;
   private float CheckSphere;
   public float gravity = -0.3f;
   public float JumpPower = 3.0f;
   private Vector3 velosity;
    // Update is called once per frame
    void Update()
    {
     float h = Input.GetAxis("Horizontal");
     float v = Input.GetAxis("Vertical");
     Vector3 mouse = (transform.right*h+transform.forward*v)*speed*Time.deltaTime;
     controller.Move(mouse*speed*Time.deltaTime);
    
    velosity.y +=gravity*Time.deltaTime;
    controller.Move(velosity*Time.deltaTime);
    isGraunded=Physics.CheckSphere(Sphere.position,CheckSphere,sloy);
    if(isGraunded&&velosity.y < 0)
    {
     velosity.y += -2f;
    }
      if(Input.GetButtonDown("Jump")&&isGraunded)
      {
       velosity.y = Mathf.Sqrt(JumpPower*-2f*gravity);
      }
     

     
     }
}
 hello