---
title: IMetaDataDispenserEx::GetOption 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008783"
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption 메서드
현재 메타 데이터 범위에 지정 된 옵션의 값을 가져옵니다. 옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `optionId`  
 진행 검색할 옵션을 지정 하는 GUID에 대 한 포인터입니다. 지원 되는 Guid 목록은 설명 섹션을 참조 하세요.  
  
 `pValue`  
 제한이 반환 된 옵션의 값입니다. 이 값의 형식은 지정 된 옵션 형식의 변형이 됩니다.  
  
## <a name="remarks"></a>설명  
 다음 목록에서는이 방법에 대해 지원 되는 Guid를 보여 줍니다. 설명에 대 한 자세한 내용은 [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) 메서드를 참조 하세요. 이 `optionId` 목록에 없는 경우이 메서드는 `E_INVALIDARG` 잘못 된 매개 변수를 나타내는 HRESULT를 반환 합니다.  
  
- MetaDataCheckDuplicatesFor  
  
- MetaDataRefToDefCheck  
  
- MetaDataNotificationForTokenMovement  
  
- MetaDataSetENC  
  
- MetaDataErrorIfEmitOutOfOrder  
  
- MetaDataGenerateTCEAdapters  
  
- MetaDataLinkerOptions  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
