---
title: ICorPublishProcess::IsManaged 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: 3eec84624866b2be7068d7875cd650828c283fd2
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421100"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged 메서드
이 [ICorPublishProcess](icorpublishprocess-interface.md) 에서 참조 하는 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbManaged`  
 제한이 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 부울 값에 대 한 포인터입니다. `true`프로세스에 관리 되는 코드가 있으면 값이이 고, 그렇지 않으면 `false` 입니다.  
  
## <a name="remarks"></a>설명  
 현재 버전의에서는 `ICorPublishProcess` 관리 코드가 있는 프로세스에 대 한 액세스만 허용 하므로는 `IsManaged` 항상를 반환 `true` 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorPublishProcess 인터페이스](icorpublishprocess-interface.md)
