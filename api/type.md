```typescript
type CodeTemp = {
    "Name": string;
    "Type": string;
    "Path": string;
}

type AppConfig = {
    "mc_server_root_path": string;
    "mc_server_proxy_root_path": string;
    "theme": string;
    "qq_bot": boolean;
    "qq_bot_port": number;
    "llonebot_token": string;
    "qq_group": string;
}

type McServerConfig = {
    "server-name": string;
    "gamemode": string;
    "force-gamemode": string;
    "difficulty": string;
    "allow-cheats": string;
    "max-players": string;
    "online-mode": string;
    "allow-list": string;
    "server-port": string;
    "server-portv6": string;
    "enable-lan-visibility": string;
    "view-distance": string;
    "tick-distance": string;
    "player-idle-timeout": string;
    "max-threads": string;
    "level-name": string;
    "level-seed": string;
    "default-player-permission-level": string;
    "texturepack-required": string;
    "content-log-file-enabled": string;
    "compression-threshold": string;
    "compression-algorithm": string;
    "server-authoritative-movement-strict": string;
    "server-authoritative-dismount-strict": string;
    "server-authoritative-entity-interactions-strict": string;
    "player-position-acceptance-threshold": string;
    "player-movement-action-direction-threshold": string;
    "server-authoritative-block-breaking-pick-range-scalar": string;
    "chat-restriction": string;
    "disable-player-interaction": string;
    "client-side-chunk-generation-enabled": string;
    "block-network-ids-are-hashes": string;
    "disable-persona": string;
    "disable-custom-skins": string;
    "server-build-radius-ratio": string;
    "allow-outbound-script-debugging": string;
    "allow-inbound-script-debugging": string;
    "script-debugger-auto-attach": string;
}

type OsState = {
    "CpuCores": number;
    "CpuUsage": number;
    "MemoryUsage": number;
    "OsMemory": number;
}

type Plugin = {
    "PluginName": string;
    "Manifest": string;
}

type ProcessState = {
    "pid": string;
    "cpu": number;
    "memory": number;
    "runTime": string;
}

type ServerStatus = {
    "motd"?: string | null;
    "protocol"?: number | null;
    "version"?: string | null;
    "players_online"?: number | null;
    "players_max"?: number | null;
    "server_id"?: string | null;
    "level_name"?: string | null;
    "gamemode_id"?: string | null;
    "port_v4"?: number | null;
    "port_v6"?: number | null;
}

export class ConPtyProcess {

    /** Creates a new ConPtyProcess instance. */
    constructor($$source: Partial<ConPtyProcess> = {}) {

        Object.assign(this, $$source);
    }

    /**
     * Creates a new ConPtyProcess instance from a string or object.
     */
    static createFrom($$source: any = {}): ConPtyProcess {
        let $$parsedSource = typeof $$source === 'string' ? JSON.parse($$source) : $$source;
        return new ConPtyProcess($$parsedSource as Partial<ConPtyProcess>);
    }
}

export class OrdinaryProcess {

    /** Creates a new OrdinaryProcess instance. */
    constructor($$source: Partial<OrdinaryProcess> = {}) {

        Object.assign(this, $$source);
    }

    /**
     * Creates a new OrdinaryProcess instance from a string or object.
     */
    static createFrom($$source: any = {}): OrdinaryProcess {
        let $$parsedSource = typeof $$source === 'string' ? JSON.parse($$source) : $$source;
        return new OrdinaryProcess($$parsedSource as Partial<OrdinaryProcess>);
    }
}
```