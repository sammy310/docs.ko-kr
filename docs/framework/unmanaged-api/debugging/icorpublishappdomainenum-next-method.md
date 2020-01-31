---
title: ICorPublishAppDomainEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: c8866e98be0dd064138acdf5e0f6fb9c339fb3d2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790641"
---
# <a name="icorpublishappdomainenumnext-method"></a>ICorPublishAppDomainEnum::Next 메서드
현재 위치에서 시작 하 여 현재 프로세스에 있는 지정 된 수의 응용 프로그램 도메인을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `celt`  
 진행 검색할 요소의 수입니다.  
  
 `objects`  
 제한이 각각 응용 프로그램 도메인을 나타내는, 검색 된 [ICorPublishAppDomain](icorpublishappdomain-interface.md) 개체의 배열에 대 한 포인터입니다.  
  
 `pceltFetched`  
 제한이 실제로 반환 된 응용 프로그램 도메인의 수에 대 한 포인터입니다. `celt` 일 경우이 값은 null 일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorPublishAppDomainEnum 인터페이스](icorpublishappdomainenum-interface.md)
