---
description: '자세히 알아보기: IMetaDataImport:: GetParamProps 메서드'
title: IMetaDataImport::GetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
ms.openlocfilehash: 2c48215836dfb3ae44edc9a2bf10d4028fd82bb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728121"
---
# <a name="imetadataimportgetparamprops-method"></a>IMetaDataImport::GetParamProps 메서드

지정한 ParamDef 토큰이 참조하는 매개 변수에 대한 메타데이터 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `tk`  
 진행 메타 데이터를 반환할 매개 변수를 나타내는 ParamDef 토큰입니다.  
  
 `pmd`  
 제한이 매개 변수를 사용 하는 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `pulSequence`  
 제한이 메서드 인수 목록에 있는 매개 변수의 서 수 위치입니다.  
  
 `szName`  
 제한이 매개 변수의 이름을 저장할 버퍼입니다.  
  
 `cchName`  
 진행 에서 요청 된 크기 (와이드 문자) `szName` 입니다.  
  
 `pchName`  
 제한이 의 와이드 문자에서 반환 되는 크기입니다 `szName` .  
  
 `pdwAttr`  
 제한이 매개 변수와 연결 된 특성 플래그에 대 한 포인터입니다. 값의 비트 마스크입니다 `CorParamAttr` .  
  
 `pdwCPlusTypeFlag`  
 제한이 매개 변수가 임을 지정 하는 플래그에 대 한 포인터입니다 <xref:System.ValueType> .  
  
 `ppValue`  
 제한이 매개 변수에서 반환 하는 상수 문자열에 대 한 포인터입니다.  
  
 `pcchValue`  
 제한이 `ppValue` 와이드 문자 단위의 크기 이거나, `ppValue` 가 문자열을 포함 하지 않는 경우 0입니다.  
  
## <a name="remarks"></a>설명

매개 변수의 시퀀스 값은 `pulSequence` 1로 시작 합니다. 반환 값의 시퀀스 번호는 0입니다.

## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
