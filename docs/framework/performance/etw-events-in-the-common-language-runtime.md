---
title: 공용 언어 런타임의 ETW 이벤트
description: CLR (공용 언어 런타임)에서 ETW (Windows 용 이벤트 추적) 이벤트와 관련 된 요약 및 보기 링크를 읽습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: e1da57abba559cdb1e54071c103d67b5327c30ac
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553703"
---
# <a name="etw-events-in-the-common-language-runtime"></a>공용 언어 런타임의 ETW 이벤트
CLR(공용 언어 런타임)은 다양한 디버깅 및 프로파일링 이벤트를 통해 ETW(Windows용 이벤트 추적) 진단 정보에 대한 유용한 이벤트 추적을 제공합니다. CLR ETW 이벤트는 Windows ETW 추적 시스템을 사용하여 공용 언어 런타임에서 제공되는 기존 프로파일링 및 디버깅 지원을 확장합니다.  
  
 ETW에 대 한 자세한 내용은 ETW를 [사용한 디버깅 및 성능 조정 개선](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) 문서에 나와 있습니다. Xperf에 대한 자세한 내용은 NTDebugging 블로그의 [Windows Performance Toolkit - Xperf](/archive/blogs/ntdebugging/windows-performance-toolkit-xperf)(Windows 성능 도구 키트 - Xperf) 항목에서 찾을 수 있습니다.  
  
 .NET Framework 4 이상은 이벤트 항목에 설명 된 모든 이벤트에 필요 합니다. Windows Vista 운영 체제가 최소 지원 클라이언트이고, Windows Server 2008이 최소 지원 서버입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [.NET Framework 로깅 제어](controlling-logging.md)  
 ETW 이벤트를 캡처하고 보기 위한 도구와 명령을 설명합니다.  
  
 [CLR ETW 공급자](clr-etw-providers.md)  
 런타임 및 런다운 공급자와 ETW 데이터 수집에 이러한 공급자를 사용하는 방법을 설명합니다.  
  
 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)  
 범주별 이벤트 필터링을 가능하게 하는 런타임 및 런다운 공급자에 대한 키워드를 설명합니다.  
  
 [CLR ETW 이벤트](clr-etw-events.md)  
 CLR ETW 이벤트, 해당 키워드 및 이벤트 데이터를 자세히 설명합니다.  
  
## <a name="see-also"></a>참조

- [ETW Events in the .NET Framework](etw-events.md)
