---
description: '자세히 알아보기: IMetaDataImport:: GetMemberRefProps 메서드'
title: IMetaDataImport::GetMemberRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: b441f39d95c9af1e18d34a1a4d86d6cea33508c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783882"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>IMetaDataImport::GetMemberRefProps 메서드

지정한 토큰이 참조하는 멤버와 연결된 메타데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `mr`  
 진행 연결 된 메타 데이터를 반환할 MemberRef 토큰입니다.  
  
 `ptk`  
 제한이 TypeDef 또는 TypeRef 또는 멤버를 선언 하는 클래스를 나타내는 TypeSpec 토큰 또는 멤버를 선언 하는 모듈 클래스를 나타내는 ModuleRef 토큰 또는 멤버를 나타내는 MethodDef 토큰입니다.  
  
 `szMember`  
 제한이 멤버의 이름에 대 한 문자열 버퍼입니다.  
  
 `cchMember`  
 진행 에서 요청 된 크기 (와이드 문자) `szMember` 입니다.  
  
 `pchMember`  
 제한이 의 와이드 문자에서 반환 되는 크기입니다 `szMember` .  
  
 `ppvSibBlob`  
 제한이 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `pbSig`  
 제한이 의 크기 (바이트) `ppvSigBlob` 입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
