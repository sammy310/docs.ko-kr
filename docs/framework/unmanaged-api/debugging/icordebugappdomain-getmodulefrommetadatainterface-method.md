---
title: ICorDebugAppDomain::GetModuleFromMetaDataInterface 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
ms.openlocfilehash: 5dede67412711736d269386a20446cf45fab1619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672203"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a>ICorDebugAppDomain::GetModuleFromMetaDataInterface 메서드

지정 된 메타 데이터 인터페이스에 해당 하는 모듈을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pIMetaData`  
 진행 [메타 데이터 인터페이스](../metadata/metadata-interfaces.md)중 하나인 개체에 대 한 포인터입니다.  
  
 `ppModule`  
 제한이 지정 된 메타 데이터 인터페이스에 해당 하는 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
