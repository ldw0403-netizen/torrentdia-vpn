# torrentdia-vpn

TorrentDia 앱이 시작할 때 이 저장소의 `servers.json`을 읽어 서버 목록을 갱신합니다.
앱을 새로 설치하지 않고 이 파일만 고치면 됩니다. (저장소는 반드시 **Public**)

## servers.json 쓰는 법

```json
{
  "disable": ["US-FREE-127"],
  "speedpick": ["US"],
  "add": []
}
```

- `disable`: 앱 목록에서 뺄 서버 이름 (느리거나 막힌 서버)
- `speedpick`: 속도 측정으로 가장 빠른 서버를 고를 나라 (예: `["US","JP"]`). 비워 두면 핑이 가장 낮은 서버로 바로 연결 (게임용)
- `add`: 서버 추가. 항목 예시:

```json
{"n":"US-MY-1","c":"US","l":"US 내서버","k":"<내 개인키>","p":"<서버 공개키>",
 "e":"1.2.3.4:51820","a":"10.0.0.2/32","d":"10.0.0.1"}
```

> 주의: `add`에 넣는 `k`(개인키)는 Public 저장소에서 누구나 볼 수 있습니다.
> 개인키가 필요한 서버는 앱에 직접 넣거나, 노출돼도 괜찮은 키만 쓰세요.

## 올리는 법 (웹에서)
1. github.com 에서 New repository → 이름 `torrentdia-vpn`, Public
2. Add file → Upload files → `servers.json`, `README.md` 올리고 Commit
3. 끝. 앱이 `https://raw.githubusercontent.com/ldw0403-netizen/torrentdia-vpn/main/servers.json` 을 읽습니다.
