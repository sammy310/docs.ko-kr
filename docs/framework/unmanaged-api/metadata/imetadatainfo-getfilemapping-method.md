---
description: '자세히 알아보기: IMetaDataInfo:: GetFileMapping 메서드'
title: IMetaDataInfo::GetFileMapping 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
ms.openlocfilehash: 82a1a23c50a4d8340804f66966933fc6a11e0f8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688483"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping 메서드

매핑된 파일의 메모리 영역 및 매핑 유형을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppvData`  
 제한이 매핑된 파일의 시작에 대 한 포인터입니다.  
  
 `pcbData`  
 제한이 매핑된 영역의 크기입니다. `pdwMappingType`가 이면 `fmFlat` 파일의 크기입니다.  
  
 `pdwMappingType`  
 제한이 매핑의 유형을 나타내는 [CorFileMapping](corfilemapping-enumeration.md) 값입니다. CLR (공용 언어 런타임)의 현재 구현은 항상를 반환 `fmFlat` 합니다. 다른 값은 나중에 사용할 수 있도록 예약되어 있습니다. 그러나 이후 버전 또는 서비스 릴리스에서 다른 값을 사용할 수 있기 때문에 항상 반환 된 값을 확인 해야 합니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|모든 출력이 채워집니다.|  
|`E_INVALIDARG`|NULL이 인수 값으로 전달 되었습니다.|  
|`COR_E_NOTSUPPORTED`|CLR 구현은 메모리 영역에 대 한 정보를 제공할 수 없습니다. 이 문제는 다음과 같은 이유로 발생할 수 있습니다.<br /><br /> -메타 데이터 범위가 또는 플래그를 사용 하 여 열렸습니다 `ofWrite` `ofCopyMemory` .<br />-메타 데이터 범위가 플래그 없이 열렸습니다 `ofReadOnly` .<br />- [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타 데이터 부분만 여는 데 사용 되었습니다.<br />-파일이 PE (이식 가능한 실행 파일) 파일이 아닙니다. **참고:**  이러한 조건은 CLR 구현에 따라 달라 지 며 CLR의 이후 버전에서 약화 될 가능성이 높습니다.|  
  
## <a name="remarks"></a>설명  

 가 가리키는 메모리는 `ppvData` 기본 메타 데이터 범위가 열려 있는 동안에만 유효 합니다.  
  
 이 메서드가 작동 하려면 [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) 메서드를 호출 하 여 디스크에 있는 파일의 메타 데이터를 메모리에 매핑하면 플래그를 지정 해야 `ofReadOnly` 하며 또는 플래그를 지정 하지 않아야 합니다 `ofWrite` `ofCopyMemory` .  
  
 각 범위에 대 한 파일 매핑 형식의 선택은 CLR의 지정 된 구현과 관련이 있습니다. 사용자가 설정할 수 없습니다. CLR의 현재 구현은 항상 `fmFlat` `pdwMappingType` 를 반환 하지만이는 이후 버전의 clr 또는 지정 된 버전의 이후 서비스 릴리스에서 변경 될 수 있습니다. 서로 다른 레이아웃과 오프셋이 있으므로 항상에서 반환 된 값을 확인 해야 합니다 `pdwMappingType` .  
  
 세 매개 변수 중 하나에 대해 NULL을 전달 하는 것은 지원 되지 않습니다. 메서드는 `E_INVALIDARG` 를 반환 하 고 출력은 채워지지 않습니다. 매핑 형식이 나 영역의 크기를 무시 하면 비정상적인 프로그램이 종료 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataInfo 인터페이스](imetadatainfo-interface.md)
- [CorFileMapping 열거형](corfilemapping-enumeration.md)
