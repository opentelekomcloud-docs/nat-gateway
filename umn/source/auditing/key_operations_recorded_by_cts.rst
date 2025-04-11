:original_name: nat_cts_0001.html

.. _nat_cts_0001:

Key Operations Recorded by CTS
==============================

You can use CTS to record operations on NAT Gateway for query, auditing, and backtracking.

:ref:`Table 1 <nat_cts_0001__en-us_topic_0107344478_table1419082716297>` lists public NAT gateway operations that can be recorded by CTS.

:ref:`Table 2 <nat_cts_0001__table18203355141715>` lists private NAT gateway operations that can be recorded by CTS.

.. _nat_cts_0001__en-us_topic_0107344478_table1419082716297:

.. table:: **Table 1** Public NAT gateway operations

   ============================== ============= ================
   Operation                      Resource Type Trace
   ============================== ============= ================
   Creating a public NAT gateway  natgateway    createNatGateway
   Modifying a public NAT gateway natgateway    updateNatGateway
   Deleting a public NAT gateway  natgateway    deleteNatGateway
   Creating a DNAT rule           dnatrule      createDnatRule
   Modifying a DNAT rule          dnatrule      updateDnatRule
   Deleting a DNAT rule           dnatrule      deleteDnatRule
   Creating an SNAT rule          snatrule      createSnatRule
   Modifying an SNAT rule         snatrule      updateSnatRule
   Deleting an SNAT rule          snatrule      deleteSnatRule
   ============================== ============= ================

.. _nat_cts_0001__table18203355141715:

.. table:: **Table 2** Private NAT gateway operations

   =============================== =============== =====================
   Operation                       Resource Type   Trace
   =============================== =============== =====================
   Creating a private NAT gateway  privateNat      createPrivateNat
   Modifying a private NAT gateway privateNat      updatePrivateNat
   Deleting a private NAT gateway  privateNat      deletePrivateNat
   Creating a DNAT rule            privateDnatRule createPrivateDnatRule
   Modifying a DNAT rule           privateDnatRule updatePrivateDnatRule
   Deleting a DNAT rule            privateDnatRule deletePrivateDnatRule
   Creating an SNAT rule           privateSnatRule createPrivateSnatRule
   Modifying an SNAT rule          privateSnatRule updatePrivateSnatRule
   Deleting an SNAT rule           privateSnatRule deletePrivateSnatRule
   Creating a transit subnet       transitSubnet   createTransitSubnet
   Modifying a transit subnet      transitSubnet   updateTransitSubnet
   Deleting a transit subnet       transitSubnet   deleteTransitSubnet
   Assigning a transit IP address  transitIp       createTransitIp
   Releasing a transit IP address  transitip       deleteTransitIp
   =============================== =============== =====================
