# Directions API
##### A guide to using Mapfit's Directions API

---
### Introduction

Mapfit offers an easy to use Directions API. All you need is a post request with some parameters.

### Getting Started

For a Starting Point in your directions you can use either source-address parameter or source-location and for a destination you can use either destination-address or destination-location. You will also need to have an API key that you can get [here](https://javascript.mapfit.com/docs/get-api-key).

Familiar with [Postman](https://www.getpostman.com/)? Download and run our postman collection below to get started with API examples in seconds.

[![Run in Postman](https://files.readme.io/3178ec7-POSTMANPIC.png)](https://s3.us-east-2.amazonaws.com/mapfit-test-assets/180521_Mapfit_REST_API.postman_collection.json)

### Options

These are the options for a post request.

Parameters | Type | Explanation| |
-----------|------|------------|-----------|
source-address| Object| This is an object that containing the street address of the starting location | `{ "street_address" : "119 W 24th St", "locality" : "New York", "admin_1" : "NY" }`
source-location | Object| This is an object that containing the lat/lng of the starting location | ` { "lat" : 40.74405, "lon" : -73.99324 }`
destination-address| Object| This is an object that containing the street address of your destination| `{ "street_address" : " 660 Madison Ave, "locality" : "New York", "admin_1" : "NY" }` 
destination-location| Object| This is an object that containing the lat/lng of the starting location| `{ "lat" : 40.74405, "lon" : -73.99324 }` 
type| String| This is the type of directions you want to receive| "walking"

### POST Get Directions (via Address)
A sample POST request is seen below. Make sure to include your API key in the call.

[https://api.mapfit.com/v2/directions?api_key={YOUR_API_KEY}](https://api.mapfit.com/v2/directions?api_key={YOUR_API_KEY})

### Body
```json
{
  "source-address": {
    "street_address": "119 W 24th St",
    "locality": "New York",
    "admin_1": "NY",
    "zip": "10001",
    "entrance_type": "all-pedestrian"
  },
  "destination-address": {
    "street_address": "107 Sacred Heart Lane",
    "locality": "Reisterstown",
    "admin_1": "MD",
    "zip": "21136",
    "entrance_type": "all-pedestrian"
  },
  "type": "driving"
}
```


### POST Get Directions (via Coordinates)
A sample POST request is seen below. Make sure to include your API key in the call.

[https://api.mapfit.com/v2/directions?api_key={YOUR_API_KEY}](https://api.mapfit.com/v2/directions?api_key={YOUR_API_KEY})

### Body
```json
{
  "source-location": {
    "lat": "40.744040",
    "lon": "-73.993198",
    "entrance_type": "all-pedestrian"
  },
  "destination-location": {
    "lat": "40.654579",
    "lon": "-73.973964",
    "entrance_type": "all-pedestrian"
  },
  "type": "driving"
}
```

### Example Response

```json
{
    "trip": {
        "summary": {
            "min_lon": -76.829399,
            "max_lat": 40.78091,
            "max_lon": -73.989159,
            "length": 203.525,
            "time": 12404,
            "min_lat": 39.378174
        },
        "status_message": "Found route between points",
        "legs": [
            {
                "summary": {
                    "min_lon": -76.829399,
                    "max_lat": 40.78091,
                    "max_lon": -73.989159,
                    "length": 203.525,
                    "time": 12404,
                    "min_lat": 39.378174
                },
                "shape": "wayulAzceclCvX_|@se@uZ{e@s[ke@c[ke@c[{e@c[se@c[se@s[_]`fAil@xiBsAdEyHjVgIhWeExMwl@tkB_JfYyz@pmCqC|IcQ|i@eY`|@_hAos@uIuD{KwDeFkAaGyBmFiCwHeEkFgDiHcF}E_J_CoHsB_IyAoIu@sG_DgXmE_TyC{KeD{JqH{KiH_J_TqQgHaIyCgC{EyBsF}@gDm@iCN_Dl@}Dz@qCzAwChB_EvDeEpGaHzLcFzKiHtO{FhL{FjLqGzK{KrPgD`HoCbGyBtEaC`GkBbGgC~Hm@jBiClIgDlKkAtEiB`HcB`G{ApHgH|^cBxLaCzKgDzK_D|JuwFtpQc}F`}QqCjKyBjLyAzKu@xLe@hMGtNNzLd@xLbAxLrAjLbBzKnChLfDjL|DzK|E|JjF|IrFrGjG`HdZzUjKnIzFrEpGfEdFvCjFvCjFjB`MdEvSnHdFxBjFhCbFfDdEvCtEvDfJ`HfCxBnDhB~C|@~C\\~C?pCOfDk@zEmAlFyBrEgClEgDvDuE~CeFhCaGhBaHjA_Il@qHF_IOeF]sEm@eFcAuEkAcFkBuEyBuEwCuDqCiC_DiC{EgC{FiC}EyBgIgDqLeEsKwDcLeE{KwCkLgDsKwCc[qHyLiCsLyBqLiB{LiBqL{AoIkAsF_@mE?uE?uDNeE\\_E|@}Dz@oDzAuExB}DxBmEvCuEdF}DtEoDrF_D`GwCrGaCpG{e@vvAmPng@{Ubq@_Xpz@kVfw@uYtcAiRdo@}Utn@oXxu@w|@h~Bgb@jiAyMj`@qVhw@ku@~mCmPbp@{J|_@cLdc@q\\ppAyq@blCcKre@_^roA{FnSoSfw@mJ`\\mEtOkLre@}Tb{@qWx_A{Uj_A{[ztAc[rmAsP|i@oCfOmA~HsAjKs@nIW~HMnIOpHNzJT~Id@nIt@nHl@dFz@`GdArGrApG~BnI`C`HxCbGjFjKbKtO~IpH|IrFrKrFzKtDfJvCv]zK`RdFhMvCpMdEfHjBjLtDzAl@pBl@ds@xWnc@jV|lAhl@v_DbbB~]`Szd@fXtTvNnTdOtTdPdTrQlT`RhSpRfS~R~RlTxRnTrQ|TxQhVpQjV|PhWzOhW|OhXlPrZnNhXhMvWnNd[fH`QlElKrLb[hMn]zhA~cDvNtc@tYrz@nh@~{AhRli@dOfc@bf@fvA|Tdn@vg@jtAvw@htBhM`\\pG`RpH~SxGlT|EpRrFlUpGfXvIfc@jFdZdEzUnDhWnCxWpCvXxBvXhBb[jAvXdAdZd@r[\\ng@|EbvM\\xa@l@~]jAl^zAp\\`Bb[rBvXfCdZpCtZtD~]fEb[tDhWlEtYjGr[jFfXbGvXxFhWlF~S|DdOzKl_@lU~r@tc@huAxRzj@|Otc@vHlU|EvNnl@j}AfSnh@pWbp@hXpp@fSdd@dOr[tP`]fItN|ItPdJtOzKpQ`MtPlKdOzKtOxLtOzP`SzPnRzQbRpQpQ`RrPpRdPxRvN~RvNvSvMvSxLfTjLdTzKtT|JtTlInYlK|YlJl^|I`cDhv@|^nI|YrF|YfEpWfCxWjAxWl@tsDbGvSz@bVzA`RxBvSxC~SdErUrFbQrFfYjKjUzKrVvNtTfNfTrPlT`SfSnSfSlUpXl^ruClcE`NbRnMbPrLfNpLhMtOtOdPdPpH`HvH`HfNzK~NjKnHtEtPjKp`Ali@tSlKdt@dZruD|{A`v@tZtPnHbP`HbRnJvRhLxRxLlTfOhRdOnSbQlT~S|TzUfI|JxHzJ~M`S`N~SzOfXvNfXxLhWfOj`@bL~]tNde@riA~aE|O~h@vIhWnN|^nNp\\dOr[lPp[|S~]|Tp\\zQjVjP`StOpQhMxLfSpR~SbQbe@n^tKrFn]~Rt^bQbtAfm@buEjrBxe@|Tjf@hWdd@zVld@vX|c@vXh_BfaAvfApq@|vBjtA~h@b[rj@n]rrBppAfr@vb@`RzKpfA`q@|gA~q@d_@lUrP|JpdB`eAvlAlt@x_BfbA||Ah`Al`CrxAzj@n]bp@vc@`k@xa@xg@z_@xf@z`@lc@l_@xb@j`@zi@ng@hg@`g@||A~{AvyC`xCvl@hl@xf@re@de@fb@`a@`]~b@~]ba@rZvW`RvY`Svb@fXfb@hW~{Ap{@hHdE`\\rQ|gAdn@nbAlj@rj@b[lOnI|J`GdKpHbK~HrPvNhS`RbQrQzOnRdPnTxM~RbPhWxMjV~MvXvI`SlO~\\jKlUjLvWzKjVbLzVzKhWrKzUpLxWlKjUxLhXtJlTdOp\\hNb[~MtZrz@dlBhLjVfNfXvNhWtOzVlOjUxRhWd_@hb@vI|IhRbRhRbPzTbQfTdPzUdO`WvNzVxLlEjBjP`HlnA|h@twAzj@f]vNp]bPth@hWje@jVre@xWhuAdx@|_@nT~f@vXdZtOpl@dZ~uA~q@~r@|^hiBn}@|x@ha@rdAxk@t~@bf@|c@jVnw@vb@~jBvaAfnDhiBvjKznFdEhBtzHt~DxnKfqFl}Ady@z`@|Tj`@jUzUtOzUtOtJpHlwB||AnX~RvWbRnY`RtTfNdThMxRjKhg@hWjU|JpWzKrvCflAvXjLnYfMrVzKvfA|i@j}Avw@bu@l_@xyBjiAhg@vXvhDrmB~`Azj@ju@fc@zy@lh@vw@li@xl@ja@jj@xa@vw@dn@vq@jj@fm@nh@dj@`g@bt@pp@xpF|bFlaBn{AhRrQvuBnoBnpAtnAteDbaDd}AnzAls@`r@td@rd@l^l_@d_@z`@n]z`@p]ha@d^fc@p\\vb@x]td@x`@zj@dF`HvSbZbVn^bU~]j\\|h@tYre@dTn^`R~\\~c@fx@~q@~qAfc@pz@`zAxrCr[tn@lYfm@hWjk@`]tx@tJjVzPre@zZl}@tUzt@rZreAzLbe@nM~g@~ChMpHrZbLpg@rK|i@dJli@lJxj@fIlj@`Izj@lI`q@zFbe@jVrmBbGre@z~@~sHxGtn@zFfm@jGls@zEvm@lZb`EtYd~DvD`g@|Ezj@rFfm@xFzj@pHvm@`H|h@nIhl@nI|h@dJli@lJ~g@dJpg@~Ibe@rK|i@|Jre@dJfc@rKbe@zKdd@lKha@zOhl@tO|i@nNdd@hNvb@|Sdn@tTfn@jVbo@jVxl@jVhk@pWjk@`Wli@vXli@pW`f@jVfc@ln@pfAfNjUrhBx}CdPtYpVvb@b[hl@rVpf@|_@vw@x[ls@pWxl@re@xjAn]l}@nc@vlAvh@byAhf@dwAnm@jiB`Wdx@|Tzu@hiCh`Jp_ApbDfIfXlUlt@xB`HrQ|h@jUdo@bLbZrUxl@hWdn@pXvm@~Wxk@vXjj@fYli@|Y~h@dZng@j[~g@jZtd@p]`g@v]pf@l^de@f^tc@t^vb@npBz}B`mHpqIp\\j`@|_@dc@foGtpHp{NxxPnSjV|pCpbD`iBtuB~l@`r@j\\j`@zP~RxG~Hf^l`@n]l^lZdZx[dZzZxWz[hWz[zUnb@rZn]|TpkAzu@x\\|S|jCrcBze@tZbe@p[voBxuAle@r[xe@tYdd@jVz`@nSln@rZpuFrwCtm@rZf`Gx}C|pCvuAx}GhhDn|@fc@~NnHl_MbhGhuApq@nkBj_AhbDx_Bzd@xVtd@hXrk@|]dc@hXfpLb{Hp_Atn@ld@`\\duHpuFp{@bo@|cA|t@tbA`q@`q@tc@ly@~g@|h@tZbp@|^pq@l_@bnAtn@dy@xa@xf@jUli@zUxk@jVdy@`]t^vMr`@vNvg@rPle@vNxf@vNddItvBpyBhk@pz@|Tvx@|TteCzu@pjFx~Aral@lkQbzAtc@zvC~|@pVpHtxJnxCffAp\\vw@jWjk@~RtlAvb@fn@zUbVnJzi@zTfs@b\\|r@rZde@`SvzAdn@bf@`Rpg@bQhGxBh\\lK~b@fNx|HnzBh]jKl}@tYfdDliAvuBhu@tcIftCje@pRzLdFldDdmAd}Ang@huA|_@psBzj@d_@lJblDdbAfm@`Shu@xVfs@jVln@zUxf@`Sxa@dOlx@b\\x{@tYry@rZvx@vYfl@~RrtAdd@zbBli@hiCp{@`GjBfs@zUt}I|yC|jHx~Bre@tOhb@xMpeAn]loDbnAb|Gz|B`wI`yCvl@~RxRrGxp@zTxyAnh@zaD~gAhgDnfA|pCj_A`QbGtmAvb@jV~Hp\\|JfNdExf@fNj[~IfmE`pArj@dOhWbGd`@jKvg@xMr_@jKxBl@vSbFpWpH|TpGlbBl_@|h@hMvvA|^hv@lU`q@|TlO`GhNrFnHxCtJtDr[vNzo@r[boA|r@jy@li@`v@|i@rj@fc@ze@xa@tZtYr_@l_@ld@dd@nXrZrVp\\h\\hb@v^pf@xa@dn@zi@dy@v]fn@r[fl@vXzk@heAz{Bzz@zhBbz@|fBrj@xkAl~@~oBdzCtpGtrAhsC~g@~fA`m@~pA|lA|eCzZzj@p\\xl@n^ro@ds@tlA~pFx`J`qEvnHnpAzsBbGzJbeExcHxqD|`GzAhCju@bnAhkEfeHrbG`zJx_BpmCzrBpmDnNxVlx@xuAjp@~eAtOzVrz@pyAbbCduDzwAl{Bb{@dxAzj@z~@biAh~BbGzLhGvMnTdd@fMfY`Sha@~b@z_AzlCt{FrPp]|aBxpDrxBlyE~f@peA~Np[`~Bv|Erk@hkAv|@lgBhf@vaAnb@`{@|xAv~CpdBzpDx~AzoDvgAl|Bfw@f`Bzd@dcAbL|ThMzVrp@zrAfw@xuAp~B|yD`CrE`HlK`LrPh]be@hGnIvSfYrQzUbFpGh]hb@rwBjqCtpBxhCd_A~pAdY|_@~b@hl@t@jAhzA|pB~tGdyId`HboJ~sH~{JhsGl}IdnAtbB`wCx{DpeFvdHv}@zsAdc@do@|Zdc@fIlKdO~RxH|J|T~]lsDnaFbVb[`fAjsAtn@dy@nm@tx@nc@xl@|kBpcCzo@ry@hRlUz_@|h@fO~Sr`@nh@jiAvuA|{AvjB~_CzqCjiBbnBrrBpxB|qAnqAfNfO~XvXdZb[lTzUx\\z_@xf@rf@boArnAlnIfwIddEb`E|pBpoBpXtY``Ah`AbVhWzZhWli@dd@lmAlhA|ZfYzhAlhApeBdlBd{B|eCz~EbhGpcCleDnsDheFxcGjtI`vIzfMhHjK~CtEzUn]fJhNbV~\\dJfNlU`]|IxMdJfMfJhNbU`\\vIhMzj@tx@vIxM|IfMpiB`nCnIhMfTp\\~HfNvIfNlIhNvIfNvS~]fItNfIvNvS|^~HvNnIdOfIfOn]bp@pRj`@hkAndC`HtO`HdPvHbPtZ`r@nHbPfm@lsApHbPpQja@hHbP|d@rdAvHdPbe@`eApRhb@pHbQbp@rxAfIbQpRfc@~HrPtmA~nCnRxb@pHrPp\\jt@`Rhb@xHrPje@beAvRha@pRz`@fIbPxHdPfh@vaA`W`g@dZ`g@ld@dy@zUz_@`Rb[~b@`r@|^zi@nYxa@tJvNbKfNtJvNnc@vl@tc@hl@dKhMvWp\\dKhMxWr[jKxLxq@hv@jKxLzKxLpLjLtKxLts@zu@~fE`kEjaH|`Hxv@p{@j`@p\\bLhLbLjLzKzKhLjLr_Ah`ArQpRfSnRvXfYbLjLbLzK`LhLbLjLpf@pf@jLjLlYtYrLxLbLjLpLhLbLzLpLhLbLjLrLjLpf@~f@bLjLxf@pf@|YdZzKjL`f@pf@~XfYrKzKde@re@jKjKrKzKjp@pp@dd@fd@dKjKjKjK|JlKvWvWzp@`q@fXhXl~@z~@zKjLzKzKrKxLjKxLrKzLtKxLbKxLrKxMlKfMzJxMlKvMfc@hl@zJfNdU~]lJfNtJvNvIvNlJvN|T|^tTl_@~Sz_@vSj`@fIdPfSha@pf@`fAhRvb@jQfc@bQvb@pGbQ|Ovb@bGbQzFbQ`GrPrFbQzFtPdFbQrFrPbFbQdFbQb[peA`Mxa@tErPbFbQtEdP~Sls@rErPfT|s@xLhb@jFbQ|E`Q|Tzu@rVxu@lOfc@hGbQ~Xzt@xGbQ`HdP|Ynr@jQj`@hHtOx[bp@j\\ro@~HvN~HdOfS~]vIrPvHvNt@zArKnR~IhNfN`Rf]hk@hSp\\vHfNfS`]nIfNf^xl@th@~|@vItNnIvNnIfNnIfNtIfNvSp]f^hl@~HvMnIfN|JrP`RtZ~HfNnIxM~HvMnS`]~HfN`IfNvHfNhHvN~HfNpHvNvHfNjo@tmAxGdObR|_@fHdO`IfOrZnq@pHdPfHtO`HrPrQja@hHbPzPxa@xGdPxGbPxGdPbGdP`HbP`HfOpGbPxGvOtOj`@rGtOpGdO|Oj`@xGdOtOl`@xGtO|Oj`@pGdOjGtOxGtOjGtOxGdPhGtOlPx`@pGvOpGtOxa@dcAb\\xu@vXdn@nHtOxRz`@f]pp@~S|_@nIdOlTl_@|T|^~IvNdJfN|IfNfJfNrUp\\lUp\\bVr[lJhMbKhMvTfXfMfOdKxLtc@ng@lKzKfXdZdJlKjWdYvWfYlKjLfXbZ|d@`h@zKxLfXdZjKhLdd@`g@lKzKfc@bf@jKhLbKzKdKzKtJjLhWvX|JzKjKjLlP`Rbj@tm@jKzKdKjLjKzKxWtY|JjLjKxLdKjLjKhL|JzLjKxLdKjLlc@|h@bWb[jo@vw@tJxMbKfM|JxM|JvMnb@jk@dKhMjKvNlJxL|JvM`Wp\\|JxM|JfNxV`\\rVp\\tJhMbVr[lJhMlJxLlJxLfJhM|IzLnIjKzUr[vIhL`a@li@~IhMpG~HnX~^lJhMnm@dx@lJhM|JhMlJhMpb@jj@lJxMry@~fAlJfM|JxMlJvMrVb\\tJfNzJvM|JhNbV~\\tJfNpa@xl@lJfN|JfN|IvN|JvNhMnRt^|i@dKfN|JvN|IdOlJhNdKfNlJtNfm@n}@bV~]dJfNtU~]tJfNjUn]lJfNz`@hl@|IfNlU`]bk@`{@nIxMbUp\\fO~S|OhVtIxM~IvMdJxM~IfNfw@jjA|IvMfJfNlJfNx`@hl@bV`]fJvMpa@zj@dJhMtJhMlUr[pa@|h@lJxLtx@beAdJxLlJxLhw@tcA|IjLlJxLvIjLlJhL|TdZdJjLbG~Ht_@pf@jj@lt@fShWpRhWnSxV~HlKxHzJp\\fc@dOpRrKfNpG~I`H|IfY|^fvAjiBrGlI~HlKnDtEtDrEdEtF~D`GzErF|d@xl@hGnIrG~H~b@hk@`H|JfI|JvHzJfI|J~H|JhSfXlIlKvSvXt_@pf@|IxL~IxLrUdZtJjLdJhMbRzUlOpRbKvMdKxMjKfNlKvMzJhNt_@~g@pMtOtm@dy@bsBtjCv|@`fAzt@dy@ly@`{@~zF~uFz{HluHlpCpmCvw@xu@ngE|cEbyEbuEnuBzqBtoDrlDpz@dx@b\\p\\lbBj~AvaEx{Dz_A|~@d`Cd`Czk@xk@tYtZxa@`f@n{A`pB~W|^x\\ng@di@p{@jVhb@~fArwB`l@lrAdK|TzKzVz_@~eApWpq@jQbf@rK`\\lJtYzo@z|BdmB~tGxdA~mDxa@dxAzUh`Ara@zhBnW~qAbLlr@lKvm@|S`{AzQv`BdEvb@xVjgCxMvuA~CdZjAlKjBpQvWdlC|~@lgJjU|{BbB`Rtx@|iIre@nwEz~@`pJ|Efc@hGhl@rLrnAtOrbBzUpcCjLlhA~MvvAhHbp@vMjtAt@`Ht@nHjUz|Bze@zyEnIp{@vq@xbHtZrlChWv`BtJhl@|Y||AfXnqAlUfaAzA`IxBnHxBpHvCfNlEtOrK|^`Mvb@zKb\\hb@`oAl}@v`Cdo@bxAdy@dbBzUfc@`q@|hA~m@x`At}@lqAt}@`pA|}@`pAhzFzaInh@jt@lTdZz|Br`D`v@pfAre@bo@lmAvaB~kAtaB~gAj}AtgAl}AdcAdwAz_AryApk@dcAz[do@zAvC`BfDzAvC`BvCfJ`SzAfDrAvCxAfDbBvCnD`I`BvCrGvMhGfNfDnIzAfD~CnIzAfD|D|I|gAvtCpfAduCdeC~uGtJxVpg@xuA`Mn]ha@peA~Xxv@xGpQj_AneCfx@bxBxdAfsCpaAdkCzt@poB`sC|tHrcA|pCdsA~mD~aAplCvdCzwGvaAtkC~dChxGhM~]fN~]tExMlOx`@bFxMpHpRhH`RtTjj@b[nr@fNb[rAhCzKjVzAvCxBbFxGfOzAfCzAvDvCpGzAhC~C`HzAvCrFxLxAxC~C`HzAvC~C`HzAvCrFzLzAvCrFxLzAhCrFxLrAvCrFzLzAvCrFxLzAvC~C`HxAxCtFxLxAhCrFxLzAvCrFxLzAxCrFxLzAvC~C`HzAvCrFzLrAfCrFhMzAhCrFxLxAvCfIrQzAvCrFzLzAfC~HrQpb@z~@hW|i@hLzU~Xfm@~Stc@rAxCvNrZrAxCrFxLxAfCtFzLxAvCfIrQ~Xfm@zAvC~HpQzAxCrKzUzAvCfIrQzAvC~HrQzAfCfIrQxAvC`D`Hl`L`cVrFxLzAvCfIrQzAvCrFjLrAvCrFxLzAxCrFxLzAvCrFzLxAvC~C`HzBdE~HrQdaGvhMveBtsD`r@n{Ap`AlrBlc@j_Adi@zhAv}@bnBxz@hiBbk@tmApp@vvAr[~q@fIrQbLzUfDpHrFxLtwAz{C|x@pdBdy@rcBdzCrgGziFdbKvHrPpW~h@ro@rnAhtBlcEhR~]`Wtd@xf@x`AzPn]hWli@ja@n|@pBdEds@nqAfYbf@fNfXrFhMvIdP~Wpf@|_@xv@|s@xtAhHdOhLlUvI`R`b@bz@v]tn@rd@l~@fTpf@|Op\\pV`g@`]ng@`dBxgDdnAjhC|JpQvMfX~m@~gAhWre@xyAbvCbLzUpq@nrA`{@x~Ap\\tn@nDlJbVtd@dE~HlYxl@tKnS~a@bz@loDl`HznJfcRns@xtAzlBruDrQp\\vq@~qAxLzU~aAlgBle@lhAtNb[xg@npAnS~h@pRjj@nH|Tln@neBj[n}@v]jiA`N|^|^peAnH`StPre@zPpf@ld@xjAh\\z_AjUtn@rQ|h@xQre@de@jsAnNj`@rUpq@dZrz@pWhv@dd@npAjj@z~Aba@ziAl_@`eAdYxv@d_@jiAlOhb@`]x`Anr@tvBdKn]fNre@nHfXtYlhArdFp|RjvDf|NdTtx@f`BxmGt_@z~AlU`eAnxCjpNjf@x}BnSvaAtxDfyQ~kBhaJb~A`rHvHl_@rVjtAbL|s@|NdcA`CnRnDxWxBpRpBdPjGjj@hBpQzAbRhBbPvDre@dJdcArF~r@rnAlxNh\\jzDbMryAnC~]rAjLpBlT|Efm@fXv~CrKnpAlE|i@jB|TrApRz@~Rt@tZz@fXl@b[jAb\\lAj_@r@b{@d@pp@rAj`@hCdZhBpRfD`\\~Db\\nHtc@fNfm@lFnTfHp[zGlU`HvXlEnS`GhWlFb[|DzVdElTnDlTnCpRpH`q@hHdn@jPryAjdAbeJ`NtlAzO~{A`h@vqEvRpeBhChW|J~{@zEj`@tEn^fNpoAd~@rfI|Eng@jAzKjFdo@fDhk@nC|i@xC|}@d@b[l@~r@\\b[Wp\\?nH]vc@kAzi@qBvm@kBr[iBrPaChXcF`f@oDr[aH|h@qGhb@oIpf@eE~SsFxVyCfNiLbf@eEdPuJn]{Lj`@cVnr@qLl_@kF`RgEfNoRxv@{sAvzFcrCz{LgdMpbi@iMzj@_qAnuFkPxv@wNx`AaCbPeKty@eDvb@mAfNwCn^qGlgAcBlUaCha@}D`r@sA|TcAbP_E|i@kAdPcArPOhBkAbQiBvXiC|^GxBUxByBj`@_D~h@yCre@qB`\\m@hMiG|rAm@zj@FzUr@dn@pBz_AhCxk@\\lJrAhb@`MbbCxHpxBjAroA}@~oB]~SwChiBkG`mDaB~{@_I~bEu@xk@m@bf@FzUbA`\\jBj`@`Lj`AfJfw@hGng@zFzj@pBpf@t@hb@sA|i@oDdd@{Fl_@mIha@yHfXiBrGkVzt@{[`q@kZzi@y\\rf@oSdZgOnSk_@|h@il@dy@{j@ju@}i@`q@il@jj@i{@~q@{j@|_@waA|s@aWlTyQnScLrPiM|TyLjViH`RwIhWyGb[}Ed[_CxVgD~g@sA|_@?nS\\fXThW`Dls@vCvc@vHdn@xBxMfD|S~CtO`M~g@fOre@lYnr@piB`bEt{ClkGhuAftC~v@n|A|c@n|@vI`R`{@dlB`q@lqBpq@f`Cd_@`dB`\\`zAhRj_AvsDn_Q|qA`iGjk@rlCly@~xDvw@ttDvMdn@t_@rcB|x@zzDzt@tiDtx@`wD~Rl}@bv@vtCjo@hiBpk@faBrLfY``AhtBlZfm@~]ro@zd@tx@dPhWvCtE~S`\\zd@pq@~h@nr@bLhMpsBviCzgBv_ChaArxAjVhb@th@tlAjtAvhDfr@lhBp_Bt~Dxa@z~@voBjdElKpR`{@jtAvb@do@p_BzqBlrAdmBlj@nr@|c@dn@vb@hk@hWb\\t_@fm@f|@faBrp@~dBrj@hjB|^zhB`]x}Bri@puE`Hjk@|gBjdOzAxLvkApeJnlAtwJrFre@x\\bmC~CdZth@hpE~Ifx@jKjiAl@pGzFn{AFdErAp\\TnTVduC?fw@Dnh@Un`GFzxFd@j~ArAzi@nCpq@hCha@|Dxb@hMh_AzQreA~Mnq@zZpzAlOhv@pl@jrCxR|}@x_AznEbfEhaSxG`]hG~\\jFb\\tE`\\tE|^nD|^fDxa@`C~]hBb[rAj`@z@xa@VjVNxLD|_@EfYWl^m@vXkAz`@iBl^yB~]yBzV_Ebe@ip@jwGmEbe@_n@rhGoHlt@}_@xzDkFzk@{Fbo@sF`r@wDjj@mDfm@iCnh@yBhk@qBhl@kAtc@mAnh@m@vb@{PvzPe@ha@aBppAm@re@sAre@qBbe@yCre@mDbf@eF|h@{Eja@{Ftc@qHbe@yG|_@cp@`bDo|@~lEkLtn@qGvb@aH`g@sFbe@eEtd@wDbf@wC~g@kBvb@qAxa@eAdd@]be@Gde@Vdd@j@vb@dAdd@hBbf@xBz_@hCvb@|Ezk@zEre@jFdc@hH`g@|mEthX`Hbe@zFrf@rFlh@nDhb@fD~g@vCvm@jAp\\t@l_@d@z_@Vl_@?ng@_@vc@cA~g@cBng@gCli@gDbf@_E`g@{Epf@}El_@sFxa@eJzi@oIvc@sK`g@yRz~@yG`]qHxa@aHtc@aGfc@eEz_@wD~^_Dj_@iC~]qBp]cBx`@qAj`@u@n^e@j`@On]?b\\V~\\\\b\\t@~]xAfb@bB~]`Cxa@nCj`@nDha@vm@|aG|pBtyRhCrZxBfY`BfY|@xVd@fYFtYOfYu@n]kArZiBfYaCfY_DvXwDvWmExWsFvX_Ip\\qwD~aOoHr[kFxVmEhWwDjVoClUyChWaCb[aBdZ}@b[e@rZMp]\\bZt@dZrAp\\pBr[`CfX|D`]~Hnh@hzAryIdKjk@fIha@bKde@fJj`@`Mre@nMrd@~Nde@pf@|{AlP`h@hu@j|B`Sxk@zUrp@vS|h@lUjj@j|B`kFpWfm@rFxMxyKt~VdU~g@`Wtn@`M`]vStn@nN~f@dJ~]|Jfc@hHp\\`Hl_@xFp\\lFn^zFha@dEl_@dEtc@vC|^hC~]hB|^hRlnE~b@bcKxBre@xCfd@lE|h@|Dz`@bFtc@tFj`@fHdd@`Ivc@~Hx`@tIl_@dKxa@bLha@pLz`@lKtZ`Lp[~N~^lJzUvNb[`MhWvMhWhNzVtNhVxuA`zBfIvMhgDnlFfYre@rUvb@tTtd@nSrd@zQre@hV`q@xRrp@|Ofm@ptBrdJzPzt@fHtY`HlUxHzUrKtZzKfXjK|TrLzUfNzUpMnShf@lt@fS`]vSj_@vNvYfNp[|Oja@~Mj`@pMfc@xGhVpHdZfHp\\`Ihb@|DzUdEtZbG`f@xhChhVxGxk@bFha@rGxb@nI`g@vHj_@rKde@xL`g@hMdd@rG|TlIxVvNhb@pMp\\tpCr|GxQtc@nNl_@~Ml_@nO`f@dJr[vHtYbLdd@vH~^nJre@dJzi@`gDhvSb[bmBxCrQnI`f@~H|^tIn^fJr[|IfXjLtY~MdZbQ`]hRr[dy@`oA|c@`q@twApyB`RtYb`AbzAlx@rnA~g@fw@tOjVfOfYhMfXlI~RjGtO~H|TnIhWjLja@lJj`@pGdZzFp[dExWnDxWvCxW~Cb[pCl_@rAlTbA|T|@jVd@tYTtYFhXoD|kOUxtBL`\\|@fYzAb[~BfYvDdZbG~\\tI|_@tK~]pQ~g@fwEt~Mvw@x}Bxz@`dCnw@nzBbq@bmB|IvXhHjVhGzVtEzUnD|TxBpQpBzVrAjU|@zVj@p\\f@z`@dJt_MbApeA|@~g@xAvc@pC~g@fDre@lErd@zFre@nHrf@tKdn@`L~g@zKdd@fNre@dKb[xM|_@`MrZlTre@xVpf@|OfYrQfYrU~\\fSxWvSxVhSnT~WhWzV|TnlI|_Hl_@b\\n^p[|XhXtZr[nXp\\vSvWj[dd@laLzlQnl@l}@p]~h@v]pf@`a@li@~|EllG`fEfpFbVb[zVb[p[j`@dUjVtYvX~XxW|YzUp\\zVp\\|ThWdOja@lUl|FlzCbj@tYhl@n]l_@zVha@r[r[vXtc@fb@x\\|^nXb\\jV`\\fXl_@pXtc@bVja@|Tdd@lTre@jPx`@|JzVhM~]pzFvxQzK`]rKjVrKjUxLlU~NxVzPzUtO~SfNdPvsH`gI|h@xk@z}TtjVfXp\\nTtY|SdZfOzUvSn^xQn]xMfYvS`f@dO|_@xLn]tJb[zKl_@rLdd@lJz_@~oBpgIt}@vsDpM`f@~Mdd@lU`q@|Sli@lU~h@rU`f@|Zzj@nSp]bVn]~Xz`@b`@`f@~]z`@f]`]pa@l^de@|^t^hXv]fXxsBl|Apg@|_@|n@li@h\\rZh\\p\\b`@fc@j[j`@j[fc@~Xxa@~Rr[hS~\\tS|_@tUbe@dUpf@dOn^nN|^`M`]xL|^fObe@hLz`@jLtc@lJz`@vIz`@lJ`f@nqAjvHlJbf@nHn]tKvc@rKx`@zK|_@vMz`@vfA`xCbLbZxuEzfM|JjVtJ|ThMvXtOdZrPtYnTp\\rUb[nXp\\ptBf`Cl_@tc@vW~]|T`]lUl_@~Rn]fTha@|Sdd@fTpg@xR`g@z{ChkIpQnh@zKp\\zK`]d_@boAbrGzfUbVty@~^rmAfw@lgC`f@~zAba@vlArZ||@nh@byAbu@npB~Xlt@ld@jiAvg@tmAbk@zrAthAjhC~iBp`Ex\\zt@zo@txAtUxk@pQdd@dPfc@rPbe@bQnh@xMfb@bPli@vN`h@~yGt_VtJ|^bKvb@xH|_@xGj`@jFxa@tEha@pCn]hBvXbBp]bAp\\l@~g@Ffb@_EzhU{A|qJN~h@bAtc@jB`g@nDjj@tDxa@bGpg@`Hrd@hHz`@tIj`@pMpg@dOpf@jQbf@hRdd@lOp[zPd[tZ~f@fsDjyFbKtOzKrPx_KpuOdvCvqE|Ybf@d_@ro@~Wng@bVbf@pWli@pWhk@vXrp@zPfb@vSzj@pRli@jQ~g@bPnh@|_DtlK`Nhb@~Mj_@tOn^dPr[|NxWtOjU|OnStO`RlOtO`RbQhStOtTfOhWtOfXdOld@jVdKbGd{BbnAdUhMbVrPnStO~MzLdPbPfXb\\|O|SrQhW`{Sl`[hW~]vXn]~Xb\\zTzU|ZdZb[fXt`Hv{Fxa@|]l^dZpb@n^rd@fb@|_@l_@bVp]jgClpChfI~pJlPrZxLnT~Nb[pGnShMxk@pLdn@|Jja@|Ols@z_@pdBnOdo@lEnRnCzKpCbQpBbRr@fNf@jU`BfkBl@|}@N|^d@`|@r@vlAV|IObF?ju@\\nh@VtvB?|qB?j_@OfY]n^wChtAaC~gA}@lh@e@zV]dOaCbz@UjLkB`f@sAtn@kAfc@e@xWgCxv@_EbcBcFttCcB`q@iCto@eDvb@cBnSgDp\\iC`RiGp\\oIbf@yMdn@oMhl@aMzj@gJxa@iGb[uEdZoCb[cBxVu@~SUr[W|T^rPz@~Sd@dO|@jKz@fOrAhLzAxMpC`RrFhWrFjVvHjVjFdObLvYz[bz@tJ|TpGrPpBtE`C`GpGtOnNz`@fOl_@tN|^tj@lrAnHnSlJb[dEnSpCbQbBnSz@fONjVu@p[}@`SaB`RaCdPoChLaDjLyFdPeKvXaWtn@oDjK}EbQcAfD{AnI}DvWcBtOkAbQu@tOUbGe@hv@WvXs@beA}@dOaCpRqBzKyBzK{Kn]uOpf@gNvb@uEpRwCfNkBhMcAbGyGbe@]bG_@`RNtOt@|TjAtY`Crp@hBha@d@`S?|T{@|TsAnSgDhW{FfXqLpf@qMnh@mTn|@iHjVyH~SgHdOsGjLuEnHmIjL{G~HeJlJcQ`SoX`\\eTvXsG~IoS~]kFlI_IzLgNlTyM|T_Tj`@mTvb@{Zrp@{P~]__@h`Ak_@dcAw^nfAiQzj@s`@twA{`@||AuJj`@sVhaAuObo@qf@~pBog@jrBuJl_@{K|^}JtYkKxWoNtYaMjVwfBncDkwBr_E_OxWcAxBab@dy@kQ~]yVjj@}i@roAu^||@gN`]{yAloD{JxWqHjU}Ib\\oIdc@gD|UoDl^{AhXs@bZWxW?`Rd@nS|@nS`BzVvDz_@~Rj_BfDtYpC`\\jAtYl@b\\OvXe@zUGl@s@fN{A`RaCnT_D|SeE~SmEpQqHzVkFdO{FvN{P`]wNjV}aBdkC_yHz{L}eCp`EyWhb@yRl^{Or\\}Oj_@sPtd@{GnSyG|TuI`]wIj`@qHx`@yGja@{Eha@mF|i@yBp\\qBha@sApg@]`f@F~g@r@fc@rAvb@hCja@nCj`@`Hdn@lFz_@hWrdBjFva@nDz`@lDfc@jBl_@bAdYl@fY\\~]E`]_@x`@s@n^cBfc@gXlmE_JrxA{Fn}@yAdZ{ArZe@zVO|S?lUNfYz@p[pBre@fEnh@zE|^~b@pbDpCjV`CjV`Bb[bA`]?~]UnS{@lTcBfXgDp\\mEfYyG`]gIp[gNtd@waBfqFmvBhcHoMfc@oOli@eOxk@kKha@oDvNeUzhAyQlhAiMbeAyB`RuTrcBuUxiBqG`f@_c@viDcG`g@}Dj`@qCb[kA|Te@tYm@re@F~g@|@dd@rAn]~Bfc@jBhWlJxv@|Inh@pH~\\zKdd@tJn^jQvl@`Rhl@|Nja@bR`f@vWdo@|O~]nSvb@|i@tbAj`@bp@th@xv@pb@`f@ts@b{@fXbZz~AlhBrd@ng@zQ~SxGnHr`@dd@|^z`@`g@|i@hv@~{@ry@n}@hg@fm@hRxWjLbQzK|StIbQrLb[nHnTlFnRhGlUxGb[dFtYdJrf@jL|h@hGlTpHvXxL~]vI|TjKlUdJ`RxMjUdTb\\nXfb@vc@ns@rZre@tZ`f@b[pg@`]|h@x\\li@tc@nr@nc@~q@zd@ju@fc@`r@lJfNvNhWjPxVtPn^dT~g@~Ntc@bLxb@`HrZpBxL|DjVbGde@tDtc@hChb@bAha@t@hb@d@tlAbAxtAVvx@Tpf@l@n]jA|_@dAfXbAjUhBp]nDbe@~Dre@lDtZ~CbZdFn^fD~SzF~]rFbZbKpg@tJxa@jGfYhLj`@nYh`AbVp{@vMre@|^~pAdPro@jKbf@`Iha@nHhb@nI|h@xGzj@vDz`@tDdd@tEry@nDj_AtDdmAxChaAzApf@`Bhl@`C~g@bArQrBtc@bF~r@zF`p@|Ebf@dJju@zFha@dJdn@nNju@dPju@bP~r@bLdc@vNbf@bP~g@vOtd@`M~]fS`f@lJb\\~H~R~MtZzFfNrGrPnI`StNdc@nIjVpB~IlA`HpAlJ?jAFjA?dEsAdFsP|TgIhLkF`HoIjL_O`RwCfDe@z@gD`Hib@rf@mObQuOpQulAl|AqCfDuO`SwH|Jq\\vb@}UdZyF`HqWp\\cBhBif@hl@uUvXgSjVms@~{@ud@jk@wq@pz@e_@td@mF`HaBjBmo@by@eYn^mJhL_JjL_m@xu@wCvDed@fm@qfAdwA_DfEgfBzfCcV`]{_@xk@sQdZauAz|BsPvXe_@bo@cG|JoSp\\uDrGuPtY{E~Hk\\|i@e@z@}S~]e@l@gIvMuFnJk@z@sFlJyCdFqGjKcAhBuF~I_DrFaHjLcU|^iM|SmUl`@qGzK_IfMyWdd@wXtd@_s@xkAmDrFkVx`@mo@peAk`@do@qQdZud@zt@ia@ro@wIfNqQdZoIxMmKrP}NjVeF~H{EpH{Vj`@u@jAcAzA}ItNaHlKgIvM_DtEgDrF{AhCiMpRm@z@oSr[_Sp\\yHxLoIxMaHzKoSb[iMnSyLnSwCtEa\\jj@kLrQgN|Ss`@~h@wNnRwH|JgIlK}Yz_@iNrQqAhBcG~HyHlJ_DtEoHlJsG~IqW`\\y`@|h@kG`I{Up[eJjLqCfDeJxLqG~Ik[fb@ig@bp@gDdEmJhMqBhCcLdOwXn^{e@tn@iW~\\aCxCqGnI{AhB{AxBmEbGyBfC}IjLc`@`g@aShWwfAtwAcLdOaq@p{@sxAdlB{t@j`Aaq@~{@aShWkQlUmOnSuc@vl@iCfDuOnSsP|T_@l@sUtZiWp\\qBfC{F`IyLbPiNpR_CvCuErGcBxBuDbFoO~S{@jAqH|Je@l@}N~RkGnIcLdOgCvD_ErFcKfNkGnIeJxLuEbGaH|JcP|SaDtE}TdZsJxMkLtOkFnH_TvX}JxM}IhMkLdOkAhB_DfEiMrPyG|IeErFmZhb@gDdEmJhMcG~HoMbQsAzA}EpGkLtOuIjL_@\\c_ArnA}O~SaLdOeP|T]^kGlIeJzLqHlJmO~RgDtEqBhCsPjUqRzUqBhCqMrPoIzK}JxMwW~]yBfDmF`Hs@jAag@pq@{e@ro@yG|Io]re@gTtYaH~IoSfYg^re@md@fm@kUb[sFnHsGnI{JxMyWn]}O~S}s@j_Aso@`{@cGnIsFnH_ShXmJvMiCfDkKvNiMrP{F~HwHlKsAhBaDdE_CfDwNrQ_EtE_CvCyBhBqCzAeEzAqoAfYui@xLun@fNuUrFwWbGmJhBoNfDcWrFol@xM{PtDkdAlUgJxBgIfCcFjBuEfDsKlJcGtEiGxAsL|@}I\\{Pl@e[zAuc@hCmTz@yM|@U}J_@mJUyM}@eYgCy`AkGu`Cs@o^kB_s@iByu@u@}Te@wN}@mJcAoIsAqGiBaHvR}JpHeElJaHhByB",
                "maneuvers": [
                    {
                        "verbal_multi_cue": true,
                        "begin_shape_index": 0,
                        "travel_mode": "drive",
                        "instruction": "Drive southeast on West 24th Street.",
                        "street_names": [
                            "West 24th Street"
                        ],
                        "length": 0.059,
                        "end_shape_index": 1,
                        "time": 8,
                        "type": 3,
                        "verbal_pre_transition_instruction": "Drive southeast on West 24th Street for 300 feet. Then Turn left onto 6th Avenue.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 1,
                        "travel_mode": "drive",
                        "instruction": "Turn left onto 6th Avenue/Avenue of the Americas.",
                        "length": 0.342,
                        "street_names": [
                            "6th Avenue",
                            "Avenue of the Americas"
                        ],
                        "end_shape_index": 8,
                        "verbal_transition_alert_instruction": "Turn left onto 6th Avenue.",
                        "time": 101,
                        "verbal_post_transition_instruction": "Continue for 3 tenths of a mile.",
                        "type": 15,
                        "verbal_pre_transition_instruction": "Turn left onto 6th Avenue, Avenue of the Americas.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 8,
                        "travel_mode": "drive",
                        "instruction": "Turn left onto West 31st Street.",
                        "length": 0.613,
                        "street_names": [
                            "West 31st Street"
                        ],
                        "end_shape_index": 20,
                        "verbal_transition_alert_instruction": "Turn left onto West 31st Street.",
                        "time": 151,
                        "verbal_post_transition_instruction": "Continue for 6 tenths of a mile.",
                        "type": 15,
                        "verbal_pre_transition_instruction": "Turn left onto West 31st Street.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 20,
                        "travel_mode": "drive",
                        "instruction": "Turn right to take the ramp toward Lincoln Tunnel.",
                        "street_names": [
                            "NY 495 West"
                        ],
                        "length": 0.18,
                        "sign": {
                            "exit_toward_elements": [
                                {
                                    "text": "Lincoln Tunnel"
                                }
                            ]
                        },
                        "end_shape_index": 29,
                        "verbal_transition_alert_instruction": "Turn right to take the ramp toward Lincoln Tunnel.",
                        "time": 33,
                        "type": 18,
                        "verbal_pre_transition_instruction": "Turn right to take the ramp toward Lincoln Tunnel.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 29,
                        "travel_mode": "drive",
                        "instruction": "Merge onto NY 495 West.",
                        "street_names": [
                            "NY 495 West"
                        ],
                        "length": 1.119,
                        "end_shape_index": 79,
                        "verbal_post_transition_instruction": "Continue for 1.1 miles.",
                        "time": 78,
                        "type": 25,
                        "verbal_pre_transition_instruction": "Merge onto NY 4 95 West.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 79,
                        "travel_mode": "drive",
                        "instruction": "Continue on NJ 495 West.",
                        "length": 3.244,
                        "street_names": [
                            "NJ 495 West"
                        ],
                        "end_shape_index": 204,
                        "verbal_transition_alert_instruction": "Continue on NJ 4 95 West.",
                        "time": 235,
                        "type": 8,
                        "verbal_pre_transition_instruction": "Continue on NJ 4 95 West for 3.2 miles.",
                        "toll": true,
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 204,
                        "travel_mode": "drive",
                        "instruction": "Take the New Jersey Turnpike exit on the left.",
                        "length": 0.644,
                        "sign": {
                            "exit_branch_elements": [
                                {
                                    "text": "New Jersey Turnpike"
                                }
                            ]
                        },
                        "end_shape_index": 241,
                        "verbal_transition_alert_instruction": "Take the New Jersey Turnpike exit on the left.",
                        "time": 58,
                        "type": 21,
                        "verbal_pre_transition_instruction": "Take the New Jersey Turnpike exit on the left.",
                        "toll": true,
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 241,
                        "travel_mode": "drive",
                        "instruction": "Merge onto New Jersey Turnpike.",
                        "street_names": [
                            "New Jersey Turnpike"
                        ],
                        "length": 60.595,
                        "end_shape_index": 1036,
                        "verbal_post_transition_instruction": "Continue for 60.6 miles.",
                        "time": 3425,
                        "type": 25,
                        "verbal_pre_transition_instruction": "Merge onto New Jersey Turnpike.",
                        "toll": true,
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 1036,
                        "length": 51.502,
                        "street_names": [
                            "New Jersey Turnpike"
                        ],
                        "verbal_transition_alert_instruction": "Keep left to stay on New Jersey Turnpike.",
                        "type": 24,
                        "toll": true,
                        "travel_mode": "drive",
                        "instruction": "Keep left to stay on New Jersey Turnpike.",
                        "end_shape_index": 1993,
                        "time": 2871,
                        "verbal_post_transition_instruction": "Continue for 51.5 miles.",
                        "verbal_pre_transition_instruction": "Keep left to stay on New Jersey Turnpike.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 1993,
                        "travel_mode": "drive",
                        "instruction": "Continue on I 295 South.",
                        "length": 5.804,
                        "street_names": [
                            "I 295 South"
                        ],
                        "end_shape_index": 2089,
                        "verbal_transition_alert_instruction": "Continue on I 2 95 South.",
                        "time": 426,
                        "type": 8,
                        "verbal_pre_transition_instruction": "Continue on I 2 95 South for 5.8 miles.",
                        "toll": true,
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 2089,
                        "travel_mode": "drive",
                        "instruction": "Continue on I 295.",
                        "length": 0.953,
                        "street_names": [
                            "I 295"
                        ],
                        "end_shape_index": 2115,
                        "verbal_transition_alert_instruction": "Continue on I 2 95.",
                        "time": 62,
                        "type": 8,
                        "verbal_pre_transition_instruction": "Continue on I 2 95 for 1 mile.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 2115,
                        "travel_mode": "drive",
                        "instruction": "Continue on I 95 South.",
                        "length": 52.997,
                        "street_names": [
                            "I 95 South"
                        ],
                        "end_shape_index": 2848,
                        "verbal_transition_alert_instruction": "Continue on I 95 South.",
                        "time": 2979,
                        "type": 8,
                        "verbal_pre_transition_instruction": "Continue on I 95 South for 53 miles.",
                        "toll": true,
                        "travel_type": "car"
                    },
                    {
                        "verbal_multi_cue": true,
                        "begin_shape_index": 2848,
                        "travel_mode": "drive",
                        "instruction": "Take exit 67 on the right onto White Marsh Boulevard toward White Marsh.",
                        "length": 0.145,
                        "sign": {
                            "exit_branch_elements": [
                                {
                                    "consecutive_count": 2,
                                    "text": "White Marsh Boulevard"
                                },
                                {
                                    "text": "MD 43"
                                }
                            ],
                            "exit_number_elements": [
                                {
                                    "text": "67"
                                }
                            ],
                            "exit_toward_elements": [
                                {
                                    "consecutive_count": 1,
                                    "text": "White Marsh"
                                },
                                {
                                    "text": "Middle River"
                                }
                            ]
                        },
                        "end_shape_index": 2853,
                        "verbal_transition_alert_instruction": "Take exit 67 on the right.",
                        "time": 9,
                        "type": 20,
                        "verbal_pre_transition_instruction": "Take exit 67 on the right onto White Marsh Boulevard toward White Marsh. Then Keep right to take White Marsh Boulevard.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 2853,
                        "travel_mode": "drive",
                        "instruction": "Keep right to take White Marsh Boulevard toward White Marsh.",
                        "length": 0.452,
                        "sign": {
                            "exit_branch_elements": [
                                {
                                    "consecutive_count": 2,
                                    "text": "White Marsh Boulevard"
                                },
                                {
                                    "consecutive_count": 1,
                                    "text": "MD 43 West"
                                }
                            ],
                            "exit_toward_elements": [
                                {
                                    "consecutive_count": 1,
                                    "text": "White Marsh"
                                },
                                {
                                    "text": "US 1"
                                }
                            ]
                        },
                        "end_shape_index": 2865,
                        "verbal_transition_alert_instruction": "Keep right to take White Marsh Boulevard.",
                        "time": 30,
                        "type": 23,
                        "verbal_pre_transition_instruction": "Keep right to take White Marsh Boulevard toward White Marsh.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 2865,
                        "travel_mode": "drive",
                        "instruction": "Continue on MD 43 West/White Marsh Boulevard.",
                        "length": 3.145,
                        "street_names": [
                            "MD 43 West",
                            "White Marsh Boulevard"
                        ],
                        "end_shape_index": 2974,
                        "verbal_transition_alert_instruction": "Continue on MD 43 West.",
                        "time": 274,
                        "type": 8,
                        "verbal_pre_transition_instruction": "Continue on MD 43 West, White Marsh Boulevard for 3.1 miles.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 2974,
                        "travel_mode": "drive",
                        "instruction": "Stay straight to take the I 695 West ramp toward Towson.",
                        "street_names": [
                            "MD 43 West"
                        ],
                        "length": 0.679,
                        "sign": {
                            "exit_branch_elements": [
                                {
                                    "text": "I 695 West"
                                }
                            ],
                            "exit_toward_elements": [
                                {
                                    "text": "Towson"
                                }
                            ]
                        },
                        "end_shape_index": 3003,
                        "verbal_transition_alert_instruction": "Stay straight to take the I 6 95 West ramp.",
                        "time": 52,
                        "type": 17,
                        "verbal_pre_transition_instruction": "Stay straight to take the I 6 95 West ramp toward Towson.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 3003,
                        "travel_mode": "drive",
                        "instruction": "Merge onto Baltimore Beltway.",
                        "street_names": [
                            "Baltimore Beltway"
                        ],
                        "length": 12.683,
                        "end_shape_index": 3295,
                        "verbal_post_transition_instruction": "Continue for 12.7 miles.",
                        "time": 855,
                        "type": 25,
                        "verbal_pre_transition_instruction": "Merge onto Baltimore Beltway.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 3295,
                        "travel_mode": "drive",
                        "instruction": "Take exit 20 on the right onto MD 140/Reisterstown Road toward Garrison.",
                        "length": 0.132,
                        "sign": {
                            "exit_branch_elements": [
                                {
                                    "text": "MD 140"
                                },
                                {
                                    "text": "Reisterstown Road"
                                }
                            ],
                            "exit_number_elements": [
                                {
                                    "text": "20"
                                }
                            ],
                            "exit_toward_elements": [
                                {
                                    "consecutive_count": 1,
                                    "text": "Garrison"
                                },
                                {
                                    "text": "Pikesville"
                                }
                            ]
                        },
                        "end_shape_index": 3301,
                        "verbal_transition_alert_instruction": "Take exit 20 on the right.",
                        "time": 13,
                        "type": 20,
                        "verbal_pre_transition_instruction": "Take exit 20 on the right onto MD 1 40, Reisterstown Road toward Garrison.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 3301,
                        "travel_mode": "drive",
                        "instruction": "Keep right to take MD 140 North toward Garrison.",
                        "length": 0.103,
                        "sign": {
                            "exit_branch_elements": [
                                {
                                    "text": "MD 140 North"
                                }
                            ],
                            "exit_toward_elements": [
                                {
                                    "consecutive_count": 1,
                                    "text": "Garrison"
                                }
                            ]
                        },
                        "end_shape_index": 3310,
                        "verbal_transition_alert_instruction": "Keep right to take MD 1 40 North.",
                        "time": 11,
                        "type": 23,
                        "verbal_pre_transition_instruction": "Keep right to take MD 1 40 North toward Garrison.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 3310,
                        "length": 7.668,
                        "street_names": [
                            "MD 140"
                        ],
                        "verbal_transition_alert_instruction": "Bear right onto Reisterstown Road.",
                        "type": 9,
                        "travel_mode": "drive",
                        "instruction": "Bear right onto Reisterstown Road/MD 140. Continue on MD 140.",
                        "end_shape_index": 3601,
                        "time": 651,
                        "verbal_post_transition_instruction": "Continue on MD 1 40 for 7.7 miles.",
                        "verbal_pre_transition_instruction": "Bear right onto Reisterstown Road, MD 1 40.",
                        "begin_street_names": [
                            "Reisterstown Road",
                            "MD 140"
                        ],
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 3601,
                        "travel_mode": "drive",
                        "instruction": "Turn right onto East Chatsworth Avenue.",
                        "length": 0.409,
                        "street_names": [
                            "East Chatsworth Avenue"
                        ],
                        "end_shape_index": 3616,
                        "verbal_transition_alert_instruction": "Turn right onto East Chatsworth Avenue.",
                        "time": 67,
                        "verbal_post_transition_instruction": "Continue for 4 tenths of a mile.",
                        "type": 10,
                        "verbal_pre_transition_instruction": "Turn right onto East Chatsworth Avenue.",
                        "travel_type": "car"
                    },
                    {
                        "verbal_multi_cue": true,
                        "begin_shape_index": 3616,
                        "length": 0.056,
                        "street_names": [
                            "Sacred Heart Lane"
                        ],
                        "verbal_transition_alert_instruction": "Turn right onto Sacred Heart Lane.",
                        "type": 10,
                        "travel_mode": "drive",
                        "instruction": "Turn right onto Sacred Heart Lane.",
                        "end_shape_index": 3620,
                        "time": 15,
                        "verbal_post_transition_instruction": "Continue for 300 feet.",
                        "verbal_pre_transition_instruction": "Turn right onto Sacred Heart Lane. Then Your destination will be on the left.",
                        "travel_type": "car"
                    },
                    {
                        "begin_shape_index": 3620,
                        "travel_mode": "drive",
                        "instruction": "Your destination is on the left.",
                        "length": 0,
                        "end_shape_index": 3620,
                        "verbal_transition_alert_instruction": "Your destination will be on the left.",
                        "time": 0,
                        "type": 6,
                        "verbal_pre_transition_instruction": "Your destination is on the left.",
                        "travel_type": "car"
                    }
                ]
            }
        ],
        "language": "en-US",
        "locations": [
            {
                "lon": -73.99324,
                "side_of_street": "left",
                "type": "break",
                "lat": 40.744049
            },
            {
                "lon": -76.821136,
                "side_of_street": "left",
                "type": "break",
                "lat": 39.466835
            }
        ],
        "units": "miles",
        "status": 0
    },
    "destinationLocation": [
        -76.821137,
        39.466836
    ],
    "sourceLocation": [
        -73.99324,
        40.74405
    ]
}
```