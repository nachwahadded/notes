`adb root 

`adb shell setenforce 0 &&  adb shell umount -l -t overlay /system 2> /dev/null   && adb remount
 then i go to adb shell and do 
`su 
`mount -o remount,rw /system 

| getenforce                                                                              
| Pour vérifier l'activation de sécurité                                                                                                                                                                                                                                                                  
| <span style="color: green;">**Enforcing :**</span>                                   
| bloque les actions qui enfreignent les politiques de sécurités --> le mode de fonctionnement normal pour SELinux en production, car il offre une sécurité renforcée. Ce fait avec `set enforce 1`                                                                                                                                                                                                 
| <span style="color: green;">**Permessive :**</span>                                     
| Génére des logs avec des alertes sans les bloquées --> pour le débogage et la vérification des violations potentielles avant de passer à un mode plus restrictif. Ce fait avec `set enforce 0`       