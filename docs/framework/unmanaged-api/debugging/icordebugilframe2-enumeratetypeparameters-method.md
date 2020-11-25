---
title: ICorDebugILFrame2::EnumerateTypeParameters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 73c17864047270302dbc115667eec4bf5ea1569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725048"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a>ICorDebugILFrame2::EnumerateTypeParameters 메서드

이 프레임의 매개 변수를 포함 하는 ICorDebugTypeEnum 개체를 가져옵니다 <xref:System.Type> .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppTyParEnum`  
 형식 매개 변수를 열거할 수 있도록 하는 ICorDebugTypeEnum interface 개체의 주소에 대 한 포인터입니다.  
  
 형식 매개 변수 목록에는 클래스 형식 매개 변수 (있는 경우)와 메서드 형식 매개 변수 (있는 경우)가 포함 됩니다.  
  
## <a name="remarks"></a>설명  

 [IMetaDataImport2:: EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) 메서드를 사용 하 여이 목록에 포함 된 클래스 형식 매개 변수 및 메서드 형식 매개 변수의 수를 확인 합니다.  
  
 형식 매개 변수는 항상 사용할 수 있는 것은 아닙니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
