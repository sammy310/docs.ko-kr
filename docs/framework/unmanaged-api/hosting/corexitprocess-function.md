---
description: '다음에 대 한 자세한 정보: CorExitProcess 함수'
title: CorExitProcess 함수
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: 68d33dec76387e103a34e99c529a4e7aff7535b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649587"
---
# <a name="corexitprocess-function"></a>CorExitProcess 함수

현재 관리 되지 않는 프로세스를 종료 합니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다. 대신 [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `exitCode`  
 프로세스 종료 코드를 지정 하는 정수입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> .NET Framework 4부터는 `CorExitProcess` 기존 api가 바인딩된 런타임 뿐만 아니라 프로세스에서 시작 된 모든 런타임을 종료 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
