---
title: CreateCoreClrDebugTarget 함수
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: d52757f82a950c382c7c8f2162630eda7d7795e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132101"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget 함수
원격 컴퓨터에서 실행 되는 디버거 프록시에 대 한 연결을 만들고, 원격 컴퓨터에서 실행 중인 프로세스 및 로드 된 런타임을 쿼리 하는 데 사용할 수 있는 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) 개체를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwAddress`  
 [in] 원격 대상 컴퓨터의 IPv4 주소입니다.  
  
 `ppTarget`  
 제한이 생성 될 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) 개체에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 S_OK  
 프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.  
  
 E_OUTOFMEMORY  
 `ppTarget`에 대해 충분한 메모리를 할당할 수 없습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 기타 실패  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86  
  
 **.NET Framework 버전:** 3.5 SP1
