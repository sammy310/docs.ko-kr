---
title: Silverlight 디버깅
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 49f026b8e1a3dd78a62091e77a5aba0c9a2e09d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671839"
---
# <a name="silverlight-debugging"></a>Silverlight 디버깅

이 섹션의 항목에서는 CLR(공용 언어 런타임)이 Windows 운영 체제나 Macintosh 플랫폼에서 실행 중인 Silverlight 기반 애플리케이션 디버그를 지원하기 위해 제공하는 환경 및 인터페이스를 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [EnumerateCLRs 함수](enumerateclrs-function.md)  
 프로세스의 CLR을 열거하기 위한 메커니즘을 제공합니다.  
  
 [CloseCLREnumeration 함수](closeclrenumeration-function.md)  
 [EnumerateCLRs 함수](enumerateclrs-function.md)에서 반환 된 핸들 배열에 있는 모든 유효한 CLR continue 시작 이벤트를 닫고 핸들 및 문자열 경로 배열에 대 한 메모리를 해제 합니다.  
  
 [CreateCoreClrDebugTarget 함수](createcoreclrdebugtarget-function.md)  
 프로세스 및 런타임 열거형의 원격 대상에 대한 연결을 만듭니다.  
  
 [CreateCordbObject 함수](createcordbobject-function.md)  
 원격 프로세스에서 관리되는 디버깅 세션을 인스턴스화하기 위한 기능을 제공하는 디버거 인터페이스를 만듭니다.  
  
 [CreateVersionStringFromModule 함수](createversionstringfrommodule-function.md)  
 대상 프로세스의 CLR 경로에서 버전 문자열을 만듭니다.  
  
 [CreateDebuggingInterfaceFromVersion 함수](createdebugginginterfacefromversion-function-for-silverlight.md)  
 [Createversionstringfrommodule 함수](createversionstringfrommodule-function.md)함수에서 반환 된 CLR 버전 문자열을 수락 하 고 해당 디버거 인터페이스를 반환 합니다.  
  
 [CoreClrDebugProcInfo 구조체](coreclrdebugprocinfo-structure.md)  
 원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.  
  
 [CoreClrDebugRuntimeInfo 구조체](coreclrdebugruntimeinfo-structure.md)  
 원격 컴퓨터의 프로세스에서 로드된 CLR 인스턴스를 나타냅니다.  
  
 [GetStartupNotificationEvent 함수](getstartupnotificationevent-function.md)  
 지정된 대상 프로세스에 로드 중인 CLR(공용 언어 런타임)에서 신호를 전송할 이벤트 핸들을 만들거나 엽니다.  
  
 [ICoreClrDebugTarget 인터페이스](icoreclrdebugtarget-interface.md)  
 프로세스 및 런타임 열거형의 원격 대상에 대한 연결을 만듭니다.  
  
 [InitDbgTransportManager 함수](initdbgtransportmanager-function.md)  
 프로세스 및 런타임 열거형의 원격 대상에 연결할 전송 관리자를 초기화합니다.  
  
 [ShutdownDbgTransportManager 함수](shutdowndbgtransportmanager-function.md)  
 원격 대상 컴퓨터에 대한 연결을 위해 전송 관리자를 종료합니다.  
  
## <a name="see-also"></a>참조

- [디버깅 Coclass](debugging-coclasses.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅 전역 정적 함수](debugging-global-static-functions.md)
- [디버깅 열거형](debugging-enumerations.md)
- [디버깅 구조체](debugging-structures.md)
