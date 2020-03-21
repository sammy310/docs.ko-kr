---
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
ms.openlocfilehash: 44578595b3cb790570c5359e714bd39c109cf1f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176463"
---
# <a name="corexitprocess-function"></a>CorExitProcess 함수
현재 관리되지 않는 프로세스를 종료합니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다. 대신 [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) 메서드를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `exitCode`  
 프로세스 종료 코드를 지정하는 정수입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> .NET Framework 4부터 `CorExitProcess` 시작하여 레거시 API가 바인딩된 런타임뿐만 아니라 프로세스의 모든 시작 런타임을 종료합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
