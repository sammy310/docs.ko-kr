---
title: IMetaDataConverter::GetTypeLibFromMetaData 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ab1d39ddb53e08e6fd36016f544162e2b11edb0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472072"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>IMetaDataConverter::GetTypeLibFromMetaData 메서드
포인터를 가져는 `ITypeLib` 지정 된 라이브러리 및 모듈 이름에는 형식 라이브러리를 나타내는 인스턴스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `strModule`  
 [in] 형식 라이브러리의 모듈의 이름입니다.  
  
 `strTlbName`  
 [in] 형식 라이브러리의 이름입니다.  
  
 `ppITL`  
 [out] 주소를 수신 하는 위치에 대 한 포인터를 `ITypeLib` 형식 라이브러리를 나타내는 인스턴스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IMetaDataConverter 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
