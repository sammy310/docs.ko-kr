---
title: CLRDataCreateInstance 함수
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a4a8a2fc737bbf4b49ca859f0549ca7efd54a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089772"
---
# <a name="clrdatacreateinstance-function"></a>CLRDataCreateInstance 함수
지정 된 대상 항목에 대 한 인터페이스 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 인스턴스화할 인터페이스의 식별자입니다.  
  
 `target`  
 [in] 사용자가 구현한 포인터로 [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) 인터페이스 개체를 만들 대상 항목을 나타내는 개체입니다.  
  
 `iface`  
 [out] 반환 된 인터페이스 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `ICLRDataTarget` 개체 작성기는 디버깅 응용 프로그램에 의해 구현 됩니다. 구현을 표시 되는 대상 항목의 유형에 따라 달라 집니다. 프로세스, 메모리 덤프, 원격 컴퓨터 및 등 대상 항목 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** ClrData.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 전역 정적 함수](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
