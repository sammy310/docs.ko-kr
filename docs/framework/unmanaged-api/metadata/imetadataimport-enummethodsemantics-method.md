---
title: IMetaDataImport::EnumMethodSemantics 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: 3d14aea92633c944d21d867c8152767ae6f1f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720973"
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics 메서드

지정한 메서드와 관련된 속성 및 속성 변경 이벤트를 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `phEnum`  
 [in, out] 열거자에 대 한 포인터입니다. 이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.  
  
 `mb`  
 진행 열거형의 범위를 제한 하는 MethodDef 토큰입니다.  
  
 `rEventProp`  
 제한이 이벤트 또는 속성을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rEventProp` 배열의 최대 크기입니다.  
  
 `pcEventProp`  
 제한이 에서 반환 되는 이벤트 또는 속성의 수입니다 `rEventProp` .  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 이벤트 또는 속성이 없습니다. 이 경우는 `pcEventProp` 0입니다.|  
  
## <a name="remarks"></a>설명  

 대부분의 공용 언어 런타임 형식은 *Property* 속성과 `Changed` 관련 된 속성 이벤트와 `On` *속성* `Changed` 메서드를 정의 합니다. 예를 들어 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 형식은 <xref:System.Windows.Forms.Control.Font%2A> 속성, <xref:System.Windows.Forms.Control.FontChanged> 이벤트 및 메서드를 정의 합니다 <xref:System.Windows.Forms.Control.OnFontChanged%2A> . 속성의 set 접근자 메서드가 <xref:System.Windows.Forms.Control.Font%2A> 메서드를 호출 하면이 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 메서드는 이벤트를 발생 시킵니다 <xref:System.Windows.Forms.Control.FontChanged> . 에서 MethodDef를 `EnumMethodSemantics` 사용 하 여를 호출 하 여 <xref:System.Windows.Forms.Control.OnFontChanged%2A> <xref:System.Windows.Forms.Control.Font%2A> 속성 및 이벤트에 대 한 참조를 가져옵니다 <xref:System.Windows.Forms.Control.FontChanged> .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
