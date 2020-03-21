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
ms.openlocfilehash: ef573eb9a572c27e685289b2740a55e898be2093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177625"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>IMetaDataConverter::GetTypeLibFromMetaData 메서드
지정된 라이브러리 및 `ITypeLib` 모듈 이름이 있는 형식 라이브러리를 나타내는 인스턴스에 대한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `strModule`  
 【인】 형식 라이브러리 모듈의 이름입니다.  
  
 `strTlbName`  
 【인】 형식 라이브러리의 이름입니다.  
  
 `ppITL`  
 【아웃】 형식 라이브러리를 나타내는 `ITypeLib` 인스턴스의 주소를 받는 위치에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataConverter 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
