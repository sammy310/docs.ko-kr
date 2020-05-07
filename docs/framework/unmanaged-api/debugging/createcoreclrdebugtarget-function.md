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
ms.openlocfilehash: 2271611b5cbbfe487e5798be0429ed94c227a67f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860880"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget 함수
원격 컴퓨터에서 실행 되는 디버거 프록시에 대 한 연결을 만들고, 원격 컴퓨터에서 실행 중인 프로세스 및 로드 된 런타임을 쿼리 하는 데 사용할 수 있는 [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) 개체를 반환 합니다.  
  
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
 제한이 생성 될 [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) 개체에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 S_OK  
 프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.  
  
 E_OUTOFMEMORY  
 `ppTarget`에 대해 충분한 메모리를 할당할 수 없습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 기타 실패  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86 .dll  
  
 **.NET Framework 버전:** 3.5 SP1
