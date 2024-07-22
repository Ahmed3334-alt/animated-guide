hello
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class USERCONTROL : MonoBehaviour
{
   public Light liht;
    void Update()
    {
      if(Input.GetKeyUp(KeyCode.E))
      {
         liht.enabled =  liht.enabled;

     

 }  
    }
}
