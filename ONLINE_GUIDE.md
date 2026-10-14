# Online play / 온라인 대전

## English

Both players should install or extract the same release. Check the version in the main menu footer.

1. The host opens Online, chooses a side and creates a room. Leave the port at 38567 and try automatic port mapping (UPnP).
2. Wait for the UPnP result. For players in different homes, the invitation must contain the host's public IPv4 address.
3. The host copies the invitation code. The other player pastes it, imports the address and connects. Direct IP/port entry is also available.
4. Keep the host PC and game running during the match. Connection loss pauses play; reconnect or reopen the host's saved online match.

If UPnP fails, forward UDP 38567 on the host router to the host PC's local IPv4 address, internal port 38567. Permit the game through the host PC's firewall. For manual forwarding, turn off the game's UPnP option before reopening the room. Double routers or carrier NAT may require an additional connection method.

The invitation code encodes the address; it is not a relay service. 127.0.0.1 is your own PC, and 192.168.x.x is normally a local home address. Do not use those addresses for a direct connection from another home.

F6 opens the play log; its folder button opens dated TXT/JSONL records. For a failed test, record the host/guest role, version, time, turn/round and exact status text.

## 한국어

두 사람 모두 같은 버전을 설치하거나 압축 해제합니다. 메인 메뉴 하단에서 버전을 확인하세요.

1. 방장이 온라인 메뉴에서 진영을 고르고 방을 만듭니다. 포트38567을 유지하고 자동 포트 열기(UPnP)를 시도합니다.
2. 자동 설정 결과를 기다립니다. 서로 다른 집에서는 초대 주소에 방장 공인 IPv4 주소가 들어가야 합니다.
3. 방장이 초대 코드를 복사해 상대에게 전달합니다. 상대는 코드를 붙여 넣고 주소를 가져온 뒤 접속합니다. IP/포트 직접 입력도 가능합니다.
4. 대국 중 방장 PC와 게임을 계속 켜 둡니다. 접속이 끊기면 일시 정지하며 재접속하거나 방장의 온라인 저장판으로 방을 다시 열 수 있습니다.

UPnP가 실패하면 방장 공유기에서 외부 UDP 38567을 방장 PC의 내부 IPv4 주소·내부 포트38567로 전달합니다. Windows 방화벽에서도 게임 연결을 허용합니다. 수동 전달을 쓰면 게임의 UPnP를 끄고 방을 다시 만드세요. 이중 공유기나 통신사 공유 공인 IP 환경에서는 추가 접속 방법이 필요할 수 있습니다.

초대 코드는 주소를 담는 수단이며 별도 중계 서버는 아닙니다.127.0.0.1은 자기 PC,192.168.x.x는 보통 집 안의 주소이므로 다른 집에서 직접 접속하는 주소로 쓰지 않습니다.

F6 기록 창의 폴더 버튼에서 날짜별 TXT/JSONL을 확인할 수 있습니다. 문제가 생기면 방장/참가자, 버전, 시각, 턴/라운드, 정확한 상태 문구를 함께 기록하세요.
