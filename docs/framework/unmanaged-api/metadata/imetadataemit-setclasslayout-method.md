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
ms.openlocfilehash: a18583ce807ffa672811f3a0cd1e744233f6eb30
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008835"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout 메서드
지정 된 클래스에 대 한 필드의 [레이아웃을 완료 합니다.](imetadataemit-definetypedef-method.md)  
  
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
 진행 `mdTypeDef`레이아웃을 지정할 클래스를 지정 하는 토큰입니다.  
  
 `dwPackSize`  
 진행 압축 크기는 1, 2, 4, 8 또는 16 바이트입니다. 압축 크기는 인접 한 필드 사이의 바이트 수입니다.  
  
 `rFieldOffsets`  
 진행 각각 클래스의 필드와 클래스 내의 필드 오프셋을 지정 하는 [COR_FIELD_OFFSET](cor-field-offset-structure.md) 구조체의 배열입니다. 를 사용 하 여 배열을 종료 `mdTokenNil` 합니다.  
  
 `ulClassSize`  
 진행 클래스의 크기 (바이트)입니다.  
  
## <a name="remarks"></a>설명  
 클래스는 [IMetaDataEmit::D Efin def](imetadataemit-definetypedef-method.md) 메서드를 호출 하 고 클래스의 필드에 대 한 세 가지 레이아웃 (자동, 순차 또는 명시적) 중 하나를 지정 하 여 처음에 정의 됩니다. 일반적으로 자동 레이아웃을 사용 하 고 런타임에 필드의 레이아웃을 지정 하는 가장 좋은 방법을 선택할 수 있습니다.  
  
 그러나 비관리 코드에서 사용 하는 배열에 따라 필드가 배치 되도록 할 수 있습니다. 이 경우 순차 또는 명시적 레이아웃 중 하나를 선택 하 고를 호출 `SetClassLayout` 하 여 필드 레이아웃을 완료 합니다.  
  
- 순차 레이아웃: 압축 크기를 지정 합니다. 필드는 자연 크기 또는 압축 크기에 따라 정렬 되며 필드의 오프셋은 더 작은 값으로 정렬 됩니다. `rFieldOffsets`및 `ulClassSize` 를 0으로 설정 합니다.  
  
- 명시적 레이아웃: 각 필드의 오프셋을 지정 하거나 클래스 크기와 압축 크기를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
