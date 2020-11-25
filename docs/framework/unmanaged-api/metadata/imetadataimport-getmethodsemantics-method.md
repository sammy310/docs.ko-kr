---
title: IMetaDataImport::GetMethodSemantics 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: cc01a417c3246ad2554c506f21e37a3cbbdeb991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733190"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>IMetaDataImport::GetMethodSemantics 메서드

지정 된 MethodDef 토큰이 참조 하는 메서드와 지정 된 EventProp 토큰이 참조 하는 쌍을 이루는 속성 및 이벤트 간의 관계를 나타내는 플래그를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `mb`  
 진행 의미 체계 역할 정보를 가져올 메서드를 나타내는 MethodDef 토큰입니다.  
  
 `tkEventProp`  
 진행 메서드 역할을 가져올 쌍을 이루는 속성 및 이벤트를 나타내는 토큰입니다.  
  
 `pdwSemanticsFlags`  
 제한이 연결 된 의미 체계 플래그에 대 한 포인터입니다. 이 값은 [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) 열거형의 비트 마스크입니다.  
  
## <a name="remarks"></a>설명  

 [IMetaDataEmit::D efineProperty](imetadataemit-defineproperty-method.md) 메서드는 메서드의 의미 체계 플래그를 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
