---
title: Rapports BI
keywords: BI
last_updated: June 18, 2024
tags: [BI]
summary: "liste des rapports BI"
sidebar: mydoc_sidebar
permalink: SAPwebi_rapports.html
folder: mydoc
---

<style>
  .titre-rouge {
  color: red;
  font-weight: bold; /* optionnel */
}

.accordion details {
  border: 1px solid #ddd;
  border-radius: 4px;
  margin-bottom: 0.5rem;
  padding: 0.4rem 0.6rem;
  background: #f8f9fa;
}

/* 2e niveau : un peu décalé visuellement */
.accordion details details {
  margin-top: 0.4rem;
  margin-left: 1rem;
  background: #ffffff;
}

.accordion summary {
  cursor: pointer;
  font-weight: 600;
  list-style: none;
}

.accordion summary::-webkit-details-marker {
  display: none; /* enlève le triangle par défaut */
}

.accordion summary::before {
  content: "▸";
  display: inline-block;
  margin-right: 0.4rem;
  transition: transform 0.2s ease;
}

/* flèche tournée quand c'est ouvert */
.accordion details[open] > summary::before {
  transform: rotate(90deg);
}

.accordion ul {
  margin-top: 0.4rem;
  margin-bottom: 0;
}
</style>

<div class="accordion">

<details>
  <summary>
  <span class="titre-rouge">contrôle_données_SAP</span> : vérification des données SAP
</summary>
  <details>
    <summary>attributs</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdO_tZliyEpBniIOod_3tnA" target="blank">check_HER_et_BCE</a> : surfaces avec attributs non-recours herbicides (HER) et bande culturale extensive (BCE) (incompatibles)</li> 
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AY5t7nS5c_VGpuuYJ5FS_2o" target="blank">list_surfBio_sans_HER_v4</a> : surfaces BIO éligibles sans attributs HER </li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AWNwvUWtai5EsQms78YX1Vk" target="blank">check_valeur_année_d'engagement_parbetpar</a> : comparaison par betpar surf. insc. non-rec. PPh 24-25 (vérifier durée d'engagement)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AXlKrnPm_aRMqY2SHBgsWfM" target="blank">check_ARF_et_BCE</a> : surfaces avec attributs non-recours PPh grandes cultures (ARF) et bande culturale extensive (BCE) (incompatibles)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AVouHcTjnO1Kk8rK88ovEHc" target="blank">check_attributs_et_inscriptions</a> : vérifier insc. PPh exploitation <-> attribut sur les surfaces</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ATU25SDvH29Gocd1Uk1Mk50" target="blank">check_GIWR_et_BCE</a> : surfaces avec attributs céréales rangées larges (GIWR) et bande culturale extensive (BCE)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AVHbyVOBdrNHlWr8OoBENnQ" target="blank">check_valeur_année_d'engagement</a> : vérifier durée d'engagement </li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AXpH1yQ7htRLro19Gk9U5vA" target="blank">liste_surfBio_sans_HER_vquic</a> : surfaces BIO éligibles sans attributs HER</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AXwq6d_F_gtNi2sawBkop1k" target="blank">liste_surfBio_sans_HER</a> : surfaces BIO éligibles sans attributs HER</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Ac0xLOCYzXdDrW8g_wEIpDo" target="blank">liste_Bio_sans_HER</a> : surfaces BIO éligibles sans attributs HER </li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ARsD0WJdQd1AjjIj4fLofpQ" target="blank">liste_surfBio_sans_HER_v3</a> : surfaces BIO éligibles sans attributs HER</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Aa6eu6YiSdhIjjA_WQ7qZW0" target="blank">check_durée_engagement_HER</a> : vérifier durée d'engagement surfaces avec attribut HER</li>
    </ul>
  </details>

    <details>
    <summary>biodiversité</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AWmt88S..rNCg3HxzyeFa4I" target="blank">check_céréalesrangéeslarges_surfréseau</a> : surf. céréales rangées larges <> surf. réseau</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AVe4gfaNifVAp07IGILGp5s" target="blank">check_surfaces_réseau</a> : surf. réseau sans num. réseau ; surf. réseau > surf. exp. ; surf. réseau > surf. SPB1 ; num. réseau sans surf. réseau ; surf. réseau sans droit contrib.</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ARUHxGaWU21Foxao83IiQKY" target="blank">check_surfaces_SPB</a> : surf. SPB1 <> surf. exploitée ; surf. SPB1/2 > surf. exploitée ; cc. SPB sans surf. SPB1 ; surf. SPB2 > surf. SPB1 ; année SPB non valide ; année SPB sans surf. SPB ; surf. SPB sans droit contrib. ; droit contrib. sans surf. SPB</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdvXxNGPeLdEqQ9YmW1eBhY" target="blank">check_ratio_nbre_arbres_921-924_908A-B</a> : nombre de 908/921/922/923/924 par m2 (plausibilité)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Ad6w3M_oUwdPhdG8iawXqXM" target="blank">liste_nbr_min_arbres_q1</a> : vérifier nombre minimal arbres Q1 atteint</li>
    </ul>
  </details>
  <details>
    <summary>estivage</summary>
    <ul>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ASWrmzVcv1tMgRcKOMTRD10" target="blank">check_charges_usuelle_effective</a> : vérifications PN autorisés <-> PN estivés</li>
    </ul>
  </details>  
  <details>
    <summary>exploitations</summary>
    <ul>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AWxBrABbr9JNt9ZIyWf82Og" target="blank">liste_exploitations_99_numBDTA</a> : ne doit pas être en forme 99 si num. BDTA !!! TODO : num. bdta pas encore dans la BI</li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AWYA7YAWYEhGpjJd0YEtG7Y" target="blank">liste_exploitations_liées_supp</a> : exploitation avec exploit. parent ou enfant marquée pour supp. </li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AQXcas5f9blPvfzPP3LMCfw" target="blank">liste_réductions_formExp</a> : réductions sur exploitations de forme non valide (vérif. par ex. pas saisie sous forme 2)</li>
      
    </ul>
  </details>
  <details>
    <summary>mode de culture - OC </summary>
    <ul>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AbZdYmuPusFPjttw528FuQk" target="blank">check_PI_BIO_grandescult</a> : vérification cohérence BIO/PI mode de culture <-> OC (grandes cultures)</li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZR4pDsUJ3VFrAPQ1SYCbmA" target="blank">check_PI_BIO_aromatiques</a> : vérification cohérence BIO/PI mode de culture <-> OC (plantes aromatiques)</li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AQ90oAQNSCxBu7uaxmu_WhE" target="blank">check_PI_BIO_tout</a> : vérification cohérence BIO/PI mode de culture <-> OC (tout)</li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AcEusIknoPBMrTzdVZfGnjI" target="blank">check_PI_BIO_arbo</a> : vérification cohérence BIO/PI mode de culture <-> OC (arboriculture)</li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AfJSSGPhS4hBsa_i4.cZbR4" target="blank">check_PI_BIO_petits_fruits</a> : vérification cohérence BIO/PI mode de culture <-> OC (petits fruits)</li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AS5VTTG75IpHkNgz6Sl0YO8" target="blank">check_PI_BIO_viti</a> : vérification cohérence BIO/PI mode de culture <-> OC (viticulture)</li>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Aa17XUbrQPFPu6vLv1pKF2c" target="blank">check_PI_BIO_maraich</a> : vérification cohérence BIO/PI mode de culture <-> OC (maraichage)</li>
    </ul>
  </details>
  <details>
    <summary>code de culture - OC</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AR2QdueY0ZBKvqKw5rKATcE" target="blank">check_exploit_sans_OC</a> : exploit. forme 1 ou 6 sans OC</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AeunWVKsxkJMvlH6UZfQKm8" target="blank">check_OC_maraich</a> : vérification cohérence cc <-> OC (maraichage)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AX22FoS_5vdJpU4naAovJCI" target="blank">check_OC_viti</a> : vérification cohérence cc <-> OC (viticulture)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AVaE9Hovht1PgiGI_rTHSsE" target="blank">check_OC_aromatiques</a> : vérification cohérence cc <-> OC (plantes aromatiques)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdOj_TqsHK9FqHrges5zYUY" target="blank">check_OC_ptsfruits</a> : vérification cohérence cc <-> OC (petits fruits)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AatFwpaOuKRKj2_eljZ9Joo" target="blank">check_OC_arbo</a> : vérification cohérence cc <-> OC (arboriculture)</li>
</ul>
  </details>
  <details>
    <summary>OC</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdLlug4juYdJkKD36KtIW94" target="blank">check_cotisations</a> : avec No. cotisation mais sans OC cotisation ; avec OC cotisation mais sans No cotisation ; prélèvement sans inscription ; inscription sans prélèvement</li>
    </ul>
  </details>
  <details>
    <summary>parcelles</summary>
    <ul>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AWncw_Xje7JPmfivEtBRvq4" target="blank">check_parcelles_obsoletes_avec_surfaces</a> : surf. sur parc. PA NV / à traiter / supp.  / TC NV</li>
    </ul>
  </details>
  <details>
    <summary>redevances</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AXyOxW7egc5PkaE1wh6URxs" target="blank">check_cmp_ratioProprio_surfaces_vs_parcelles_ccRedev</a> : ratio part propriétaire au niveau surface != ratio part propriétaire au niveau parcelle</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ATuDGM6iaxVJva9pP3QTNo8" target="blank">check_parcelles_propriétaires_ccRedevance_v2_OK_viti</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Ab5JFXWiIudDsx2VkQQzNaM" target="blank">check_cmp_ratioProprio_surfaces_vs_parcelles_ccRedev_viti</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AfRI0srZwKNHhhiIJi18uio" target="blank">check_parcelles_propriétaires_ccRedevance_v2_OK_sansViti</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ATUpTc7z621JhxjvO92uQQ0" target="blank">check_cmp_ratioProprio_surfaces_vs_parcelles_ccRedev_sansViti</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AXmsuM_lfhhLtqmxUXTxNNc" target="blank">check_parcelles_propriétaires_ccRedev_v2</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AalNIbmQbF1Lgv6WfeBkhx8" target="blank">check_parcelles_propriétaires_ccRedevance_v3_OK_viti</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AYI1kjH0s4tJqMzvdg4jRVk" target="blank">check_parcelles_propriétaires_ccRedevance_v3_OK_sansViti</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AefuWxzpJjNImmVMBJ63fLY" target="blank">check_propriétaires_non_valides</a> : parcelles/surfaces cc redev et propriétaire non valide</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AepJJCSo1ApBnEk60595mqs" target="blank">check_surfaces_propriétaires_ccRedev_v2_sansViti</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ASzMeTWlhqRDkwNGye5kaeE" target="blank">check_parcelles_propriétaires_ccRedevance_v3_OK</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AV_Eko5m589Io6ATA1MNLv8" target="blank">check_parcelles_propriétaires_ccRedevance_v2_OK</a></li>
    </ul>
  </details>
    <details>
    <summary>surfaces</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdSqiY.hXeFJpvu55fgLnYg">check_espèces_arbo</a> : surf. arbo avec espèce manquante</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AaqjIb2LsLJPg.RZCkx15i8">check_animaux_paturages</a> : exploitations avec bétail sans pâturages ou avec pâturages sans animaux</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Af63efMXG_JOg9v1vP11ASQ">check_surface_sans_flag_exploitée</a> : surf. sans le flag "exploité"</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZ3IuoL98FFKib4nSxDwiNY">check_surfaces_propriétaires</a> : somme surf. exploitée - somme surf. proprio</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ARK8qIJaBExOs1uiDqzlCJc">check_surfaces_zones</a> : surf. avec cc SAU hors zones 31-54 et surf. avec cc 930/931 hors zone 61</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AV6dUqdZr8FIk.6SPJw9_.8">check_surfaces_validées_avec_commentPC</a> : surf. avec commentaire PC mais n'ayant pas le statut "non validé"</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Acn4GrcVG21BnujD9O4Ez.g">check_pentes</a> : vérification somme surfaces pente</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdbpKqXBTVdBkEGQs0B4UgQ">check_animaux_paturages_exploit_avec_UP</a> : vérification animaux et pâturages, en tenant compte des UP / TODO - A CORRIGER</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AfGuXReWil5HrROvJKD.HB0">check_surfaces_variétés</a> : vérification surf. variété (variétés et comparaison avec surf. exploitée)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AUqbrIInzJlMhoHhbt0eCO0">check_cc_valides</a> : surfaces avec code culture non valides</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AYnl9tt5txpOjkUU34lNs8E">check_surfexp_0</a> : surfaces avec surf. exp. = 0 et < 5</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AfnEYJCL.kxKgEq4k273QoE">check_surfaces_par_parcelle</a> : somme surf. exp. > surf. totale parcelle</li>
    </ul>
  </details>
  <details>
    <summary>UP</summary>
    <ul>
      <li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AYPE1ulE7u9CnEhBmj3E6No" target="blank">check_inscriptions_forme2</a> : vérification inscriptions de l'UP présentes dans l'exploitation parent</li>
    </ul>
  </details>
</details>

<details>
  <summary>
     <span class="titre-rouge">listes_données_SAP</span> : extraction des données SAP</summary>
  <details>
    <summary>autres</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdpLs2tBUfdEh5qqOWsh7Ho" target="blank">liste_cotisations</a> : liste des cotisations</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZ5RLm7mJpRDiR8k4i8QvKA" target="blank">liste_inscriptions</a> : liste des inscriptions ou demandes de contributions</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ARP0QqUlFLxGjFA7nzwBz9c" target="blank">liste_réductions</a> : liste des réductions</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AULMtHi47NxGmAX88FmcfXM" target="blank">liste_localisation_UP_avec_bétail</a> : liste exploitations de forme 2 avec leur exploitation parent et localisation ; comparaison bétail enfant - parent </li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AW5nZuYayJpHhm36EDS_AwE" target="blank">liste_inscriptions_indications</a> : liste complète inscriptions/demandes de contributions + indications générales</</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AWbAfzw5X.FCqZgBujdb3wU" target="blank">liste_inscriptions_SST_SRPA_bio</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=ATpyesxpPWhAqcrayVuxIH8" target="blank">liste_indications_générales</a> : liste indications générales</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AQ3O25JmrahNsQ5W0UCugzk" target="blank">liste_exploitations_exploitants</a></li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AWkLTl8IzXVLmY0fli6ijso" target="blank">liste_statut_marital</a> : liste avec information sur le statut marital des exploitants</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZb75_QyKLFKooTCi_LbF3U" target="blank">liste_charges_usuelle_effective</a> : liste charges usuelle et effective ; nombre d'alpages et nombre d'alpages par catégorie d'animaux</li>
    </ul>
  </details>
    <details>
    <summary>exploitations</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZalIxDr7wNHlirtaSTDChk" target="blank">liste_forme1_avec_parent6</a> : liste des exploitations de forme 1 avec parent de forme 6 ; vérification des inscriptions</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AYiClw27T15EpR4zIoKw.uI" target="blank">liste_forme2_avec_parent</a> : liste exploitations de forme 2 avec leur parent</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZy5WE0qT_5MpbI6O2bZry0" target="blank">liste_exploitations_parents_avec_forme</a> : liste exploitations enfant avec exploitations parent et enfants du parent, avec formes</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AUKfuVp9XnlEkk85MRBxrSk" target="blank">liste_exploitants</a> : liste exploitants (noms et année naissance)</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZh4lbWMSThKnFHNi7LR8D4" target="blank">liste_parent_UP_avec_loc</a> : liste UP avec parent et leur localisation</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=Acj1kDohKeBCo02HMFdFrBU" target="blank">liste_exploitations_membres</a> : liste des exploitations et membres récursifs / TODO !!! ongoing </li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AT0z0I5IYDtPt5Yr_tqY.5U" target="blank">liste_exploitations_parents_enfants</a> : liste des exploitations et leur parent et enfant</li>
    </ul>
  </details>

  <details>
    <summary>surfaces</summary>
    <ul>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AaKmuq_wJXZDhoFxDkoCSOs" target="blank">liste_surfaces_attributsCTA</a> : liste de toutes les surfaces avec CTA</li> 
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AdmU_SVo3KZJiOEZ0H7jsVI" target="blank">liste_surf_réseau_nonvalidRR</a> : liste surfaces réseau non validées</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AZEaQkyqzRBGiJW2fNeUs0g" target="blank">liste_surfaces_attributs</a> : liste de toutes les surfaces avec attribut</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AeTA09kmCSpPgpAXqq2iXwA" target="blank">surfaces_compensation_horsCE</a> : données part min. de SPB pour exploit. hors CE</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AX3qcKMc2OpAoej5l.7oDiA" target="blank">surfaces_compensation_CE</a> : données part min. de SPB pour exploit. dans CE</li>
<li><a href="https://bi.vs.ch/BOE/OpenDocument/opendoc/openDocument.jsp?sIDType=CUID&iDocID=AaBv7pTsP.FHryOHRLYFUG8" target="blank">liste_surfaces_non_valides</a> : liste des surfaces avec exploitation "non validées" par PA OU sur parcelles "non validées" ou sur parcelles  marquées pour supp. OU Cultivat = N</li>
    </ul>
  </details>
</details>
</div>
