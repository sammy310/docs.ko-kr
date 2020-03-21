---
title: IMetaDataEmit::SetClassLayout 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177566"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout 메서드
[정의TypeDef 메서드에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대 한 사전 호출에 의해 정의 된 클래스에 대 한 필드의 레이아웃을 완료 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 【인】 배치할 클래스를 지정하는 `mdTypeDef` 토큰입니다.  
  
 `dwPackSize`  
 【인】 포장 크기: 1, 2, 4, 8 또는 16 바이트. 압축 크기는 인접 필드 사이의 바이트 수입니다.  
  
 `rFieldOffsets`  
 【인】 [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) 구조의 배열로, 각 구조는 클래스의 필드와 클래스 내의 필드의 오프셋을 지정합니다. 을 통해 `mdTokenNil`배열을 종료합니다.  
  
 `ulClassSize`  
 【인】 클래스의 크기(바이트)입니다.  
  
## <a name="remarks"></a>설명  
 클래스는 처음에 [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드를 호출 하 고 클래스의 필드에 대 한 세 가지 레이아웃 중 하나를 지정 하 여 정의: 자동, 순차적 또는 명시적. 일반적으로 자동 레이아웃을 사용하고 런타임에서 필드를 배치하는 가장 좋은 방법을 선택하도록 합니다.  
  
 그러나 관리되지 않는 코드가 사용하는 배열에 따라 필드를 배치할 수 있습니다. 이 경우 순차 적 또는 명시적 레이아웃을 선택하고 호출하여 `SetClassLayout` 필드의 레이아웃을 완료합니다.  
  
- 순차 적 레이아웃: 압축 크기를 지정합니다. 필드는 자연 크기 또는 보압 크기에 따라 정렬되며, 필드의 간격띄우기가 작아지게 됩니다. 설정 `rFieldOffsets` `ulClassSize` 및 0으로 설정합니다.  
  
- 명시적 레이아웃: 각 필드의 오프셋을 지정하거나 클래스 크기와 압축 크기를 지정합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
