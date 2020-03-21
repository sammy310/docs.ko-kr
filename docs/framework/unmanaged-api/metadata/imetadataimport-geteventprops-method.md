---
title: IMetaDataImport::GetEventProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177263"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps 메서드
선언 유형, 대리자에 대한 추가 및 제거 메서드, 플래그 및 기타 관련 데이터를 포함하여 지정된 이벤트 토큰으로 표시되는 이벤트에 대한 메타데이터 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,
   [out] LPCWSTR       szEvent,
   [in]  ULONG         cchEvent,
   [out] ULONG         *pchEvent,
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,
   [out] mdMethodDef   *pmdRemoveOn,
   [out] mdMethodDef   *pmdFire,
   [out] mdMethodDef   rmdOtherMethod[],
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ev`  
 【인】 이벤트를 나타내는 이벤트 메타데이터 토큰으로 메타데이터를 가져옵니다.  
  
 `pClass`  
 【아웃】 이벤트를 선언하는 클래스를 나타내는 TypeDef 토큰에 대한 포인터입니다.  
  
 `szEvent`  
 【아웃】 에서 참조하는 이벤트의 이름입니다. `ev`  
  
 `pchEvent`  
 【인】 의 넓은 문자로 `szEvent`요청된 길이입니다.  
  
 `pdwEventFlags`  
 【아웃】 의 넓은 문자로 `szEvent`반환 된 길이 .  
  
 `ptkEventType`  
 【아웃】 이벤트 유형을 나타내는 TypeRef 또는 TypeDef <xref:System.Delegate> 메타데이터 토큰에 대한 포인터입니다.  
  
 `pmdAddOn`  
 【아웃】 이벤트에 대한 처리기를 추가하는 메서드를 나타내는 메타데이터 토큰에 대한 포인터입니다.  
  
 `pmdRemoveOn`  
 【아웃】 이벤트에 대 한 처리기를 제거 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pmdFire`  
 【아웃】 이벤트를 발생 시키는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `rmdOtherMethod`  
 【아웃】 이벤트와 관련된 다른 메서드에 대한 토큰 포인터 의 배열입니다.  
  
 `cMax`  
 [in] `rmdOtherMethod` 배열의 최대 크기입니다.  
  
 `pcOtherMethod`  
 【아웃】 에서 반환되는 토큰 `rmdOtherMethod`수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
