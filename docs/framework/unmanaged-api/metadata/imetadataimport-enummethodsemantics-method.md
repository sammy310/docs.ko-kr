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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175462"
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
 【인, 아웃】 열거형에 대한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.  
  
 `mb`  
 【인】 열거형의 범위를 제한하는 MethodDef 토큰입니다.  
  
 `rEventProp`  
 【아웃】 이벤트 또는 속성을 저장하는 데 사용되는 배열입니다.  
  
 `cMax`  
 [in] `rEventProp` 배열의 최대 크기입니다.  
  
 `pcEventProp`  
 【아웃】 에서 반환되는 이벤트 또는 `rEventProp`속성 의 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 이벤트 나 속성이 없습니다. 이 경우 `pcEventProp` 0입니다.|  
  
## <a name="remarks"></a>설명  
 많은 공통 언어 런타임 형식은 *속성과* `Changed` 관련된 속성 이벤트 및 `On` *속성* `Changed` 메서드를 정의합니다. 예를 들어 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 형식은 <xref:System.Windows.Forms.Control.Font%2A> 속성, 이벤트 <xref:System.Windows.Forms.Control.FontChanged> 및 메서드를 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 정의합니다. <xref:System.Windows.Forms.Control.Font%2A> 속성 호출 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 메서드의 설정 된 접근자 메서드차례로 이벤트를 발생 합니다. <xref:System.Windows.Forms.Control.FontChanged> 속성 및 `EnumMethodSemantics` 이벤트에 대 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 한 참조를 얻으려면 MethodDef를 사용 하 여 호출 합니다. <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.Font%2A>  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
