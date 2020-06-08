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
ms.openlocfilehash: 3b47d1559300a462ccda42bc88da43f66c1043ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491305"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps 메서드
선언 형식, 대리자에 대 한 추가 및 제거 메서드, 모든 플래그 및 기타 관련 데이터를 포함 하 여, 지정 된 이벤트 토큰이 나타내는 이벤트에 대 한 메타 데이터 정보를 가져옵니다.  
  
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
 진행 메타 데이터를 가져올 이벤트를 나타내는 이벤트 메타 데이터 토큰입니다.  
  
 `pClass`  
 제한이 이벤트를 선언 하는 클래스를 나타내는 TypeDef 토큰에 대 한 포인터입니다.  
  
 `szEvent`  
 제한이 에서 참조 하는 이벤트의 이름 `ev` 입니다.  
  
 `pchEvent`  
 진행 의 와이드 문자에서 요청 된 길이입니다 `szEvent` .  
  
 `pdwEventFlags`  
 제한이 의 와이드 문자에서 반환 되는 길이입니다 `szEvent` .  
  
 `ptkEventType`  
 제한이 이벤트 유형을 나타내는 TypeRef 또는 TypeDef 메타 데이터 토큰에 대 한 포인터 <xref:System.Delegate> 입니다.  
  
 `pmdAddOn`  
 제한이 이벤트에 대 한 처리기를 추가 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pmdRemoveOn`  
 제한이 이벤트에 대 한 처리기를 제거 하는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pmdFire`  
 제한이 이벤트를 발생 시키는 메서드를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `rmdOtherMethod`  
 제한이 이벤트와 연결 된 다른 메서드에 대 한 토큰 포인터의 배열입니다.  
  
 `cMax`  
 [in] `rmdOtherMethod` 배열의 최대 크기입니다.  
  
 `pcOtherMethod`  
 제한이 에서 반환 된 토큰의 수 `rmdOtherMethod` 입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
