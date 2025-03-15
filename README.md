**DuoDev - Prison | NUI**

Ez a script lehetővé teszi, hogy NPC-t hozz létre, akivel a rendőrök (beállítható) NUI-t nyithat meg. Ebben a menüben a játékosok kezelhetik a börtön funkciókat, mint például a **berakás** és **kivételezés**. A fejlesztő dönthet úgy, hogy az interakcióhoz az `ox_target` vagy a `DrawText3D` módszert használja.

### Features / Jellemzők:

- **NPC Interakciók**: Az NPC-kkel történő interakció az `ox_target` vagy `DrawText3D` módszerrel.
- **Testreszabhatóság**: Az NPC modellje, koordinátái, iránya és viselkedése könnyen testreszabható.

### Konfigurációs beállítások / Configuration Settings:

A konfigurációs beállítások vezérlik az NPC viselkedését, valamint az egyéb jellemzőket, mint például a börtön időtartamát és a hozzáférési jogosultságokat.

#### **NPC Beállítások / NPC Settings:**
- **model**: Az NPC modellje, pl. `"s_m_m_prisguard_01"`.
- **coords**: Az NPC koordinátái, pl. `vector3(1849.3, 2584.0, 45.7)`.
- **heading**: Az NPC iránya, pl. `270.0`.
- **useOxTarget**: `true`, ha `ox_target`-ot használsz az interakcióhoz, `false` ha `DrawText3D`-ot.

#### **Egyéb beállítások / Other Settings:**
- **MaxPrisonTime**: Maximális börtön idő percben.
- **AdminGroups**: Csoportok, akik ki tudnak engedni bárkit a börtönből.
- **AllowedFactionsToJail**: Frakciók, akik megnyithatják a börtön menüt.
- **AllowedFactionsToRelease**: Frakciók, akik bárkit ki tudnak engedni.
- **Notification**: Választható értesítési rendszer, `esx` vagy `ox`.
- **JailLocation**: A hely, ahová a játékos teleportálódik börtönbe kerüléskor.
- **ReleaseLocation**: A hely, ahová a játékos teleportálódik, amikor kiengedik.

### Példa konfiguráció / Example Config:

```lua
Config = {}

Config.ESXVersion = "newESX"
Config.MaxPrisonTime = 60

Config.NPC = {
    model = "s_m_m_prisguard_01",  
    coords = vector3(1849.3, 2584.0, 45.7),  
    heading = 270.0,  
    useOxTarget = true,
}

Config.AdminGroups = {"admin", "superadmin", "mod"}
Config.AllowedFactionsToJail = {"police", "sheriff", "fbi"}
Config.AllowedFactionsToRelease = {"judge", "police"}
Config.Notification = "esx"

Config.JailLocation = vector3(1690.0, 2593.5, 45.5)
Config.ReleaseLocation = vector3(1849.2212, 2586.0576, 45.6720)
```

### Telepítés / Installation:

1. Töltsd le és helyezd a scriptet a szerver `resources` mappájába.
2. Add hozzá a `server.cfg` fájlhoz:

    ```
    ensure duodev_prison
    ```
3. Testreszabhatod a `Config.NPC` beállításokat a kívánt NPC tulajdonságokhoz.
4. Ha az `ox_target`-ot használod, győződj meg róla, hogy az telepítve van és működik a szervereden.

### Követelmények / Requirements:

- **ESX**
- **ox_target** (opcionális): Szükséges az NPC interakcióhoz, ha engedélyezve van.

### Support:

Ha bármilyen problémába ütköztél, csatlakozz a support szerverünkhöz: [Support Server](https://discord.gg/qRbWBZHZFC)

### License:

Ez a script az [MIT Licenc](https://opensource.org/licenses/MIT) alatt van licencelve.

