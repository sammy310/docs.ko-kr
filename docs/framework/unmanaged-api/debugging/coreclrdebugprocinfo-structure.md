---
title: CoreClrDebugProcInfo 구조체
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 40dbfc60f8bde1198fd56a4a8aeed1dd6879d1ae
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795627"
---
# <a name="coreclrdebugprocinfo-structure"></a>CoreClrDebugProcInfo 구조체
원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`m_dwPID`|OS에서 할당한 프로세스 식별자입니다.|  
|`m_dwInternalID`|대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 프로세스 식별자입니다. 이 식별자는 OS 식별자만큼 자주 재활용되지 않습니다.|  
|`m_wszName`|프로세스의 명령줄입니다. 이 멤버는 잘릴 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86 .dll  
  
 **.NET Framework 버전:** 3.5 SP1
