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
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177728"
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption 메서드
현재 메타데이터 범위에 대해 지정된 옵션의 값을 가져옵니다. 이 옵션은 현재 메타데이터 범위에 대한 호출을 처리하는 방법을 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `optionId`  
 【인】 검색할 옵션을 지정하는 GUID에 대한 포인터입니다. 지원되는 GUID 목록은 비고 섹션을 참조하십시오.  
  
 `pValue`  
 【아웃】 반환된 옵션의 값입니다. 이 값의 형식은 지정된 옵션 형식의 변형입니다.  
  
## <a name="remarks"></a>설명  
 다음 목록은 이 메서드에 대해 지원되는 GUID를 보여 주며 있습니다. 설명은 [IMetaData에이터Ex:SetOption 메서드를](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) 참조하십시오. 이 `optionId` 목록에 없는 경우 이 메서드는 `E_INVALIDARG`잘못된 매개 변수를 나타내는 HRESULT를 반환합니다.  
  
- 메타데이터체크중복  
  
- 메타데이터레프토데프체크  
  
- 메타 데이터 알림토큰 이동  
  
- 메타데이터세텐  
  
- 메타데이터오류이엠티아웃오브오더  
  
- 메타데이터생성TCE어댑터  
  
- 메타데이터링커옵션  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
