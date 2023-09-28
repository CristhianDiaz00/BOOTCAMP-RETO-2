//Primer Punto
alter table BOOTCAMP_CLIENTES
add NOM_CORTO VARCHAR(100)
add EDAD NUMBER(3,0);




//Segundo Punto
SET SERVEROUTPUT ON

DECLARE
   nombre_apellido varchar(100);
BEGIN
    update bootcamp_clientes
    set nom_corto = (initcap(val_nom1) ||' '|| initcap(val_ape1));
    
   FOR cliente_nom_ape IN (SELECT nom_corto FROM bootcamp_clientes) LOOP
      nombre_apellido := cliente_nom_ape.nom_corto;
      dbms_output.put_line('Nombre y Apellido: ' || nombre_apellido); 
   END LOOP;
END;




//Tercer Punto
DECLARE
   val_edad NUMBER(3,0);
BEGIN
    UPDATE bootcamp_clientes
    SET Edad = round((TRUNC(SYSDATE) - FEC_NACI) / 365);
    
   FOR cliente_edad IN (SELECT Edad FROM bootcamp_clientes) LOOP
      val_edad := cliente_edad.Edad;
      dbms_output.put_line('EDAD: ' || val_edad); 
   END LOOP;
END;




//CUARTO PUNTO
DECLARE
   v_ape1 varchar2(100);
   v_ape2 varchar2(100);
BEGIN
    UPDATE bootcamp_clientes
    SET val_ape1 = REPLACE(val_ape1,'Ñ','N'),
        val_ape2 = REPLACE(val_ape2,'Ñ','N');

   FOR cliente_val IN (SELECT val_ape1, val_ape2 FROM bootcamp_clientes) LOOP
      v_ape1 := cliente_val.val_ape1;
      v_ape2 := cliente_val.val_ape2;
      dbms_output.put_line('Cambio de letra de apellidos: ' || v_ape1 || ' ' || v_ape2); 
   END LOOP;
END;
