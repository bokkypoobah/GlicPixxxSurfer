# GlicPixxxSurfer

See https://bokkypoobah.github.io/GlicPixxxSurfer/ .

The code is mostly in [docs/index.html](docs/index.html).

Notes:

* Uses the data from https://api.glicpixxx.love/ver002/all , stored in [docs/all.js](docs/all.js).

<br />

<br />

---

GLICPIXXXVER002 Surfer

https://etherscan.io/address/0x1c60841b70821dca733c9b1a26dbe1a33338bd43#readContract

mintStartIndex 337

uint256 public BGANPUNKSV1CLAIMSTART = 0; // 74 BGANPUNKS V1
uint256 public BGANPUNKSV2CLAIMSTART = 74; // 11305 BGANPUNKS V2 - 0 + 74
uint256 public GLICPIXV1CLAIMSTART = 11379; // 37 GLICPIXXX - 11305 + 74
uint256 public DEVMINTSTART = 11416; // 84 DEVMINT - 11379 + 37
uint256 public totalGLICPIX = 11500; // 11416 + 84

function getWhichGLICPIXXYouAreGetting_BATCH(CollectionToClaim _collection, uint256[] memory tokenIds) public view returns(uint256[] memory) {
   require(mintStartIndexDrawn);

   uint256[] memory ids = new uint256[](tokenIds.length);

   if(_collection == CollectionToClaim.BGANPUNKSV1) {
       for(uint i = 0; i<tokenIds.length;i++) {
           uint tokenId = tokenIds[i];
           require(tokenId == 5389 || V1BASTARDIDs[tokenId] != 0);
           ids[i]= (V1BASTARDIDs[tokenId] + BGANPUNKSV1CLAIMSTART + mintStartIndex) % totalGLICPIX;
       }
   }
   else if (_collection == CollectionToClaim.BGANPUNKSV2) {
       for(uint i = 0; i<tokenIds.length;i++) {
           uint tokenId = tokenIds[i];
           require(tokenId < 11305);
           ids[i] = (tokenId + BGANPUNKSV2CLAIMSTART + mintStartIndex) % totalGLICPIX;
       }
   }
   else if (_collection == CollectionToClaim.GLICPIXV1) {
       for(uint i = 0; i<tokenIds.length;i++) {
           uint tokenId = tokenIds[i];
           require(tokenId < 37);
           ids[i] = (tokenId + GLICPIXV1CLAIMSTART + mintStartIndex) % totalGLICPIX;
       }
   }
   else if (_collection == CollectionToClaim.DEVMINT) {
       for(uint i = 0; i<tokenIds.length;i++) {
           uint tokenId = tokenIds[i];
           require(tokenId < 84);
           ids[i] = (tokenId + DEVMINTSTART + mintStartIndex) % totalGLICPIX;

       }
   }
   else {
       revert();
   }

   return ids;       

}



 V1BASTARDIDs[5389] = 0;
 V1BASTARDIDs[10001] = 1;
 V1BASTARDIDs[10003] = 2;
 V1BASTARDIDs[10004] = 3;
 V1BASTARDIDs[10005] = 4;
 V1BASTARDIDs[10006] = 5;
 V1BASTARDIDs[10007] = 6;
 V1BASTARDIDs[10008] = 7;
 V1BASTARDIDs[10009] = 8;
 V1BASTARDIDs[10012] = 9;
 V1BASTARDIDs[10013] = 10;
 V1BASTARDIDs[10015] = 11;
 V1BASTARDIDs[10016] = 12;
 V1BASTARDIDs[10017] = 13;
 V1BASTARDIDs[10018] = 14;
 V1BASTARDIDs[10019] = 15;
 V1BASTARDIDs[10020] = 16;
 V1BASTARDIDs[10021] = 17;
 V1BASTARDIDs[10022] = 18;
 V1BASTARDIDs[10023] = 19;
 V1BASTARDIDs[10024] = 20;
 V1BASTARDIDs[10026] = 21;
 V1BASTARDIDs[10031] = 22;
 V1BASTARDIDs[10032] = 23;
 V1BASTARDIDs[10033] = 24;
 V1BASTARDIDs[10034] = 25;
 V1BASTARDIDs[10035] = 26;
 V1BASTARDIDs[10036] = 27;
 V1BASTARDIDs[10037] = 28;
 V1BASTARDIDs[10038] = 29;
 V1BASTARDIDs[10039] = 30;
 V1BASTARDIDs[10040] = 31;
 V1BASTARDIDs[10041] = 32;
 V1BASTARDIDs[10043] = 33;
 V1BASTARDIDs[10045] = 34;
 V1BASTARDIDs[10046] = 35;
 V1BASTARDIDs[10047] = 36;
 V1BASTARDIDs[10048] = 37;
 V1BASTARDIDs[10049] = 38;
 V1BASTARDIDs[10050] = 39;
 V1BASTARDIDs[10051] = 40;
 V1BASTARDIDs[10053] = 41;
 V1BASTARDIDs[10054] = 42;
 V1BASTARDIDs[10055] = 43;
 V1BASTARDIDs[10056] = 44;
 V1BASTARDIDs[10057] = 45;
 V1BASTARDIDs[10058] = 46;
 V1BASTARDIDs[10059] = 47;
 V1BASTARDIDs[10061] = 48;
 V1BASTARDIDs[10062] = 49;
 V1BASTARDIDs[10063] = 50;
 V1BASTARDIDs[10064] = 51;
 V1BASTARDIDs[10067] = 52;
 V1BASTARDIDs[10068] = 53;
 V1BASTARDIDs[10070] = 54;
 V1BASTARDIDs[10075] = 55;
 V1BASTARDIDs[10076] = 56;
 V1BASTARDIDs[10077] = 57;
 V1BASTARDIDs[10078] = 58;
 V1BASTARDIDs[10079] = 59;
 V1BASTARDIDs[10080] = 60;
 V1BASTARDIDs[10081] = 61;
 V1BASTARDIDs[10083] = 62;
 V1BASTARDIDs[10084] = 63;
 V1BASTARDIDs[10085] = 64;
 V1BASTARDIDs[10086] = 65;
 V1BASTARDIDs[10087] = 66;
 V1BASTARDIDs[10088] = 67;
 V1BASTARDIDs[10089] = 68;
 V1BASTARDIDs[10090] = 69;
 V1BASTARDIDs[10091] = 70;
 V1BASTARDIDs[10093] = 71;
 V1BASTARDIDs[10094] = 72;
 V1BASTARDIDs[10095] = 73;
