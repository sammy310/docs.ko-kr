---
title: CorFileFlags 열거형
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: c8c2757e99b80204ad52e69a596d62c55c369965
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007418"
---
# <a name="corfileflags-enumeration"></a>CorFileFlags 열거형
[IMetaDataAssemblyEmit::D efineFile](imetadataassemblyemit-definefile-method.md)호출에 정의 된 파일 형식을 설명 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ffContainsMetaData`|파일이 리소스 파일이 아님을 나타냅니다.|  
|`ffContainsNoMetaData`|리소스 파일 일 수 있는 파일에 메타 데이터가 포함 되어 있지 않음을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
