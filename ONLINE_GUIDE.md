# Online play / 온라인 대전

[Game introduction / 게임 소개](README.md) · [Keyboard controls / 단축키](KEYBOARD_CONTROLS.md) · [Latest download / 최신 다운로드](https://github.com/oga8867/imperial-struggle-releases/releases/latest)

## English

Both players should install or extract the same release (current: v0.1.21). Check the version in the main menu footer.

1. The host opens Online, chooses a side and creates a room. Leave the port at 38567 and try automatic port mapping (UPnP).
2. Wait for the UPnP result. For players in different homes, the invitation must contain the host's public IPv4 address.
3. The host copies the invitation code. The other player pastes it, imports the address and connects. Direct IP/port entry is also available.
4. Keep the host PC and game running during the match. Connection loss pauses play; reconnect or reopen the host's saved online match.

If UPnP fails, forward UDP 38567 on the host router to the host PC's local IPv4 address, internal port 38567. Permit the game through the host PC's firewall. For manual forwarding, turn off the game's UPnP option before reopening the room. Double routers or carrier NAT may require an additional connection method.

The invitation code encodes the address; it is not a relay service. 127.0.0.1 is your own PC, and 192.168.x.x is normally a local home address. Do not use those addresses for a direct connection from another home.

F6 opens the play log; its folder button opens dated TXT/JSONL records. For a failed test, record the host/guest role, version, time, turn/round and exact status text.

## 한국어

두 사람 모두 같은 버전(현재 v0.1.21)을 설치하거나 압축 해제합니다. 메인 메뉴 하단에서 버전을 확인하세요.

1. 방장이 온라인 메뉴에서 진영을 고르고 방을 만듭니다. 포트38567을 유지하고 자동 포트 열기(UPnP)를 시도합니다.
2. 자동 설정 결과를 기다립니다. 서로 다른 집에서는 초대 주소에 방장 공인 IPv4 주소가 들어가야 합니다.
3. 방장이 초대 코드를 복사해 상대에게 전달합니다. 상대는 코드를 붙여 넣고 주소를 가져온 뒤 접속합니다. IP/포트 직접 입력도 가능합니다.
4. 대국 중 방장 PC와 게임을 계속 켜 둡니다. 접속이 끊기면 일시 정지하며 재접속하거나 방장의 온라인 저장판으로 방을 다시 열 수 있습니다.

UPnP가 실패하면 방장 공유기에서 외부 UDP 38567을 방장 PC의 내부 IPv4 주소·내부 포트38567로 전달합니다. Windows 방화벽에서도 게임 연결을 허용합니다. 수동 전달을 쓰면 게임의 UPnP를 끄고 방을 다시 만드세요. 이중 공유기나 통신사 공유 공인 IP 환경에서는 추가 접속 방법이 필요할 수 있습니다.

초대 코드는 주소를 담는 수단이며 별도 중계 서버는 아닙니다.127.0.0.1은 자기 PC,192.168.x.x는 보통 집 안의 주소이므로 다른 집에서 직접 접속하는 주소로 쓰지 않습니다.

F6 기록 창의 폴더 버튼에서 날짜별 TXT/JSONL을 확인할 수 있습니다. 문제가 생기면 방장/참가자, 버전, 시각, 턴/라운드, 정확한 상태 문구를 함께 기록하세요.

## Manual forwarding / 수동 포트 전달

If the automatic attempt fails, use the host router's port-forwarding page. The page address and field names depend on the router. The guest does not need to host a forwarded port for this setup.

자동 설정이 실패하면 방장 공유기의 포트 포워딩 메뉴를 사용합니다. 관리 주소와 항목 이름은 공유기마다 다릅니다. 이 구성에서 포트 전달을 설정하는 쪽은 방장입니다.

| Field / 항목 | Value / 값 |
| --- | --- |
| Protocol / 프로토콜 | UDP |
| External port / 외부 포트 | 38567 |
| Destination / 내부 목적지 | Host PC's current local IPv4 address / 방장 PC의 현재 내부 IPv4 주소 |
| Internal port / 내부 포트 | 38567 |

For example, if the host PC's local address is 192.168.0.20, forward external UDP 38567 to 192.168.0.20:38567. That address is only an example. The guest in another home connects to the host's public address, not to 192.168.0.20. Forwarding TCP alone does not forward this game's UDP traffic. If the host's local address changes, update the router's destination.

예를 들어 방장 PC가192.168.0.20이면 외부 UDP38567을192.168.0.20:38567로 전달합니다. 실제 PC 주소를 확인해서 넣으세요. 다른 집의 참가자는 이 내부 주소가 아니라 방장의 공인 주소로 접속합니다. TCP만 설정하면 게임의 UDP 연결이 전달되지 않습니다. PC 내부 주소가 바뀌면 공유기의 전달 목적지도 바꿉니다.

## Disconnect and resume / 끊김과 재개

- A disconnected opponent is not automatically treated as defeated. Actions pause until reconnection.
- Keep the guest's saved connection profile. Rejoining an existing seat uses the retained identity on the same PC/profile; transferring a seat to a different PC or a deleted profile has no recovery UI in this version.
- If the host closes the game, reopen it and use the saved-online-match hosting option. For the initial test, keep the original address/port and guest connection profile.
- The host stores the full online match and a separate online autosave. The guest's filtered display state is not a substitute for that host save. Offline named saves are separate.
- Restoring the host save preserves pending card/War decisions but resets previous undo history and in-progress consent requests.

- 상대의 접속이 끊겨도 자동 패배 처리하지 않고 행동을 일시 정지합니다.
- 참가자의 재접속 정보를 보관하세요. 같은 PC/프로필에 남아 있는 좌석 확인 정보를 사용합니다. PC를 바꾸거나 프로필을 지운 뒤 기존 좌석을 재발급하는 화면은 현재 없습니다.
- 방장이 게임을 종료했다면 다시 실행해 저장된 온라인 판으로 방 만들기를 선택합니다. 첫 테스트에서는 원래 주소·포트와 참가자의 연결 프로필을 유지하세요.
- 전체 온라인 판과 별도 자동 저장은 방장이 보관합니다. 참가자의 표시용 상태로 방장 저장을 대신할 수 없으며 오프라인 이름별 저장과 구분합니다.
- 저장 재개 시 카드/전쟁 선택 대기는 복원하지만 이전 되돌리기 기록과 진행 중 동의 요청은 초기화합니다.

## Expected behavior / 정상 동작 확인

| Check / 확인 | Expected / 정상 상태 |
| --- | --- |
| Shared board / 공통 지도 | Sides, Turn/Action Round, VP and public board changes agree / 진영·턴/라운드·승점·공개 지도 변화 일치 |
| Private information / 비공개 정보 | Each player sees their own hand/Ministries; hidden opponent faces stay hidden / 자기 패·내각을 보고 상대 미공개 앞면은 숨김 |
| Undo / 되돌리기 | The opponent can accept or reject an eligible request / 가능한 요청을 상대가 승인·거절 |
| First War / 첫 전쟁 | Spanish Succession follows Peace Turn 1, then the result is reviewed before Peace Turn 2's Event retention / 평화 1턴 뒤 스페인 왕위계승전쟁, 결과 확인 후 평화 2턴 카드 선택 |
| Presentation / 연출 | Each PC uses its own War presentation speed and pause/next/skip controls / 각자의 전쟁 연출 속도와 정지·다음·넘기기 사용 |

The host advances shared stages such as the end-of-War report; each required game choice belongs to its indicated player. Reading or pausing a local presentation does not transfer that decision to the other player.

전쟁 결과 확인 등 공통 단계 진행은 방장이 담당하고 필수 게임 선택은 화면에 표시된 해당 진영이 수행합니다. 자기 화면의 연출을 읽거나 멈춰도 선택 권한이 상대에게 넘어가지 않습니다.

## When connection fails / 접속 실패 확인 순서

1. Confirm that the host's room is still open and both players use the same build.
2. Check the exact IP/port carried by the invitation. A different home normally needs the host's public IPv4; a shared local network or virtual network uses an address reachable within that network.
3. Read the UPnP result. A failed attempt is not a successful forwarding rule. If using manual forwarding, check UDP, both port fields and the host PC's current local address.
4. Check the game's firewall permission. With double routers or carrier-grade NAT, forwarding on one home router may be insufficient. A suitable shared virtual network or a different hosting network may be needed.
5. Record the status text, host/guest role, version and time. Use F6 to open logs after game actions; attach only the records you have inspected for your own private information. Preserve a host save when reporting a repeatable in-game issue.

1. 방장의 방이 열려 있고 양측 게임 버전이 같은지 확인합니다.
2. 초대 코드의 IP/포트를 확인합니다. 서로 다른 집은 보통 방장 공인 IPv4를 사용합니다. 같은 공유기나 가상 네트워크에서는 그 네트워크 안에서 접속 가능한 주소를 사용합니다.
3. UPnP 결과를 읽습니다. 실패한 자동 시도만으로 포트가 열린 것은 아닙니다. 수동 전달은 UDP·외부/내부 포트·방장 PC의 현재 내부 주소를 확인합니다.
4. 게임의 방화벽 허용을 확인합니다. 이중 공유기나 통신사 공유 공인 IP 환경에서는 집 공유기 한 대의 전달로 충분하지 않을 수 있습니다. 사용할 수 있는 가상 네트워크나 다른 접속 환경이 필요할 수 있습니다.
5. 정확한 상태 문구·방장/참가자·버전·시각을 남깁니다. 게임 행동 이후 기록은 F6에서 확인하고 자기 비공개 정보가 포함됐는지 살핀 뒤 공유합니다. 게임 중 문제를 재현할 수 있다면 방장 저장도 보존하세요.

References: [Godot hosting considerations](https://docs.godotengine.org/en/stable/tutorials/networking/high_level_multiplayer.html#hosting-considerations) and [UPnP documentation](https://docs.godotengine.org/en/stable/classes/class_upnp.html). These explain the network mechanisms; actual external connectivity still depends on the players' networks.

접속 원리는 [Godot 네트워크 안내](https://docs.godotengine.org/en/stable/tutorials/networking/high_level_multiplayer.html#hosting-considerations)와 [UPnP 설명](https://docs.godotengine.org/en/stable/classes/class_upnp.html)을 참고하세요. 실제 외부 접속은 양측 네트워크 환경에 따라 확인해야 합니다.


## Cancel an unconfirmed effect / 대상 확정 전 효과 취소

Eligible Events and Advantages can be cancelled before their first actual target choice. Online, request cancellation and wait for the opponent's approval. A decline leaves the pending effect in place. Confirmation, newly drawn hidden information or a Ministry reveal can close this cancellation window. Public Event reveals and cancellations remain in the log.

가능한 이벤트·이점은 첫 실제 대상 확정 전에 사용 취소를 요청할 수 있습니다. 온라인에서는 상대가 승인해야 복원하며 거절하면 진행 중인 효과를 계속 처리합니다. 선택 확정·새 비공개 정보·내각 공개 뒤에는 취소할 수 없을 수 있습니다. 공개된 이벤트와 취소 사실은 기록에 남습니다.

## New game balance / 새 게임 밸런스

Before hosting a new match, use New Game Settings for the Spanish Empire option and −5..+5 starting TRP. Negative grants Britain; positive grants France; zero grants neither. The room shares this configuration and a resumed match preserves the remaining TRP. Both players use v0.1.21.

새 온라인 판의 방장은 새 게임 설정에서 스페인 제국과 시작 TRP −5~+5를 정합니다. 음수는 영국, 양수는 프랑스,0은 추가없음입니다. 방 설정을 공유하고 재개시 남은 TRP를 유지합니다. 두 사람 모두0.1.21을 사용하세요.
