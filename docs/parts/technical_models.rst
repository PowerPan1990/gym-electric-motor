Technical Models
################

.. toctree::
   :maxdepth: 2
   :caption: Contents:

Introduction
************
The technical models contain the technical properties of the motor, the power electronic converter and the load.

The motors and the loads can be parametrized by either choosing the number of its default set in the environment
initialization or by passing a new Load or Motor parameter dictionary as described below.
The parameters of the power electronic converter are directly included in the initialization.



DC Motor Parameter Dictionary
'''''''''''''''''''''''''''''

+----------------------------+------------------------------------------------------------+
| **Key**                    |  **Description**                                           |
+============================+============================================================+
| r_a                        | Resistance of the armature circuit in Ohm                  |
+----------------------------+------------------------------------------------------------+
| r_e                        | Resistance of the excitation circuit in Ohm                |
+----------------------------+------------------------------------------------------------+
| l_a                        | Inductance of the armature circuit in Henry                |
+----------------------------+------------------------------------------------------------+
| l_e                        | Inductance of the excitation circuit in Henry              |
+----------------------------+------------------------------------------------------------+
| l_e_prime                  | effective excitation inductance in Henry                   |
+----------------------------+------------------------------------------------------------+
| psi_e                      | effective flux linkage in Henry Ampere                     |
+----------------------------+------------------------------------------------------------+
| j                          | Moment of inertia of the motors rotor in kg/m^2            |
+----------------------------+------------------------------------------------------------+
| u_sup                      | Supply voltage of the motor in Volt                        |
+----------------------------+------------------------------------------------------------+
| i_N                        | Nominal current in Ampere (only PermEx and Series)         |
+----------------------------+------------------------------------------------------------+
| i_a_N                      | Nominal armature current in Ampere(only ExtEx and Shunt)   |
+----------------------------+------------------------------------------------------------+
| i_e_N                      | Nominal excitation current in Ampere (only ExtEx and Shunt)|
+----------------------------+------------------------------------------------------------+
| u_N                        | Nominal voltage in Volt(only PermEx, Series and Shunt)     |
+----------------------------+------------------------------------------------------------+
| u_a_N                      | Nominal armature voltage in Volt (only ExtEx)              |
+----------------------------+------------------------------------------------------------+
| u_e_N                      | Nominal excitation voltage in Volt (only ExtEx)            |
+----------------------------+------------------------------------------------------------+
| torque_N                   | Nominal torque in Nm                                       |
+----------------------------+------------------------------------------------------------+
| omega_N                    | Nominal angular velocity rad/s                             |
+----------------------------+------------------------------------------------------------+


PMSM and SynRM Parameter Dictionary
'''''''''''''''''''''''''''''''''''

+------------------+------------------------------------------------+---------------------+
| **Key**          |  **Description**                               | **Default**         |
+==================+================================================+=====================+
| r_s              | Stator Resistance in Ohm                       | 4.9                 |
+------------------+------------------------------------------------+---------------------+
| l_d              | d-axis inductance in Henry                     | 79e-3               |
+------------------+------------------------------------------------+---------------------+
| l_q              | q-axis inductance in Henry                     | 113e-3              |
+------------------+------------------------------------------------+---------------------+
| j_rotor          | Moment of inertia of the rotor                 | 2.45e-3             |
+------------------+------------------------------------------------+---------------------+
| psi_p            | Permanent linked rotor flux                    | 0.165               |
+------------------+------------------------------------------------+---------------------+
| p                | Pole pair Number                               | 2                   |
+------------------+------------------------------------------------+---------------------+


All nominal voltages and currents are peak phase values.
Therefore, data sheet values for line voltages and phase currents has to be transformed such that
:math:`U_N=\sqrt(2/3) U_L` and :math:`I_N=\sqrt(2) I_S`.

Furthermore, the angular velocity is the electrical one and not the mechanical one :math:`\omega = p \omega_{me}`.

Load Parameter Dictionary
'''''''''''''''''''''''''

+----------------------------+----------------------------------------------------------+
| **Key**                    |  **Description**                                         |
+============================+==========================================================+
| a                          | Constant term in the load equation                       |
+----------------------------+----------------------------------------------------------+
| b                          | Linear factor in the load equation                       |
+----------------------------+----------------------------------------------------------+
| c                          | Quadratic factor in the load equation                    |
+----------------------------+----------------------------------------------------------+
| j_load                     | Moment of inertia of the load                            |
+----------------------------+----------------------------------------------------------+

DC Shunt Default Models
'''''''''''''''''''''''

+----------------------------+------------------------------+
| **Key**                    |  **No 0**                    |
+============================+==============================+
| r_a                        | 2.78                         |
+----------------------------+------------------------------+
| r_e                        | 350.0                        |
+----------------------------+------------------------------+
| l_a                        | 6.3e-3                       |
+----------------------------+------------------------------+
| l_e                        | 160.0                        |
+----------------------------+------------------------------+
| l_e_prime                  | 0.94                         |
+----------------------------+------------------------------+
| j_rotor                    | 0.017                        |
+----------------------------+------------------------------+



DC Series Default Models
''''''''''''''''''''''''

+----------------------------+------------------------------+
| **Key**                    |  **No 0**                    |
+============================+==============================+
| r_a                        | 2.78                         |
+----------------------------+------------------------------+
| r_e                        | 1.0                          |
+----------------------------+------------------------------+
| l_a                        | 6.3e-3                       |
+----------------------------+------------------------------+
| l_e                        | 1.6e-3                       |
+----------------------------+------------------------------+
| l_e_prime                  | 0.05                         |
+----------------------------+------------------------------+
| j_rotor                    | 0.017                        |
+----------------------------+------------------------------+


DC Permanently Excited Default Models
'''''''''''''''''''''''''''''''''''''

+----------------------------+------------------------------+
| **Key**                    |  **No 0**                    |
+============================+==============================+
| r_a                        | 25.0                         |
+----------------------------+------------------------------+
| r_e                        | 258.0                        |
+----------------------------+------------------------------+
| l_a                        | 3.438e-2                     |
+----------------------------+------------------------------+
| psi_e                      | 18                           |
+----------------------------+------------------------------+
| j_rotor                    | 0.0017                       |
+----------------------------+------------------------------+


DC Externally Excited Default Models
''''''''''''''''''''''''''''''''''''

+----------------------------+------------------------------+
| **Key**                    |  **No 0**                    |
+============================+==============================+
| r_a                        | 0.78                         |
+----------------------------+------------------------------+
| r_e                        | 350.0                        |
+----------------------------+------------------------------+
| l_a                        | 6.3e-3                       |
+----------------------------+------------------------------+
| l_e                        | 60                           |
+----------------------------+------------------------------+
| l_e_prime                  | 0.94                         |
+----------------------------+------------------------------+
| j                          | 0.017                        |
+----------------------------+------------------------------+
| u_sup                      | 420.0                        |
+----------------------------+------------------------------+
| i_a_N                      | 50.0                         |
+----------------------------+------------------------------+
| i_e_N                      | 1.2                          |
+----------------------------+------------------------------+
| U_a_N                      | 420.0                        |
+----------------------------+------------------------------+
| U_e_N                      | 420.0                        |
+----------------------------+------------------------------+
| torque_N                   | 40.0                         |
+----------------------------+------------------------------+
| omega_N                    | 368.0                        |
+----------------------------+------------------------------+
