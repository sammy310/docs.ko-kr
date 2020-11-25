---
title: IMetaDataImport::GetParamForMethodIndex 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
ms.openlocfilehash: d4d3ba5713398876b55c072f0cda7eb5d599c4d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729288"
---
# <a name="imetadataimportgetparamformethodindex-method"></a>IMetaDataImport::GetParamForMethodIndex 메서드

지정 된 MethodDef 토큰이 나타내는 메서드의 지정 된 매개 변수를 나타내는 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `md`  
 진행 매개 변수 토큰을 반환할 메서드를 나타내는 토큰입니다.  
  
 `ulParamSeq`  
 진행 매개 변수 목록에서 요청 된 매개 변수가 발생 하는 서 수 위치입니다. 매개 변수의 번호는 1부터 시작 하며 메서드의 반환 값은 0입니다.  
  
 `ppd`  
 제한이 요청 된 매개 변수를 나타내는 ParamDef 토큰에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
