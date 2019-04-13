---
title: IMetaDataImport2::GetPEKind 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9dda1fb38546138d52b5fe61754d5497e676c37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113495"
---
# <a name="imetadataimport2getpekind-method"></a>IMetaDataImport2::GetPEKind 메서드
가져옵니다는 pe (이식 가능)에서 코드의 특성을 식별 하는 값 파일을 일반적으로 DLL 또는 EXE 파일을 현재 메타 데이터 범위에서 정의 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pdwPEKind`  
 [out] 값에 대 한 포인터를 [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) PE 파일을 설명 하는 열거형입니다.  
  
 `pdwMachine`  
 [out] 컴퓨터의 아키텍처를 식별 하는 값에 대 한 포인터입니다. 가능한 값은 다음 섹션을 참조 하세요.  
  
## <a name="remarks"></a>설명  
 참조 하는 값을 `pdwMachine` 매개 변수는 다음 중 하나일 수 있습니다.  
  
|값|컴퓨터 아키텍처|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|X64|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [CorPEKind 열거형](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
