---
description: '자세히 알아보기: CorImportOptions 열거형'
title: CorImportOptions 열거형
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: b942ed3f5b1b3c400b4f901e3dd3c4364e1d588c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784446"
---
# <a name="corimportoptions-enumeration"></a>CorImportOptions 열거형

현재 범위를 벗어난 어셈블리를 가져오는 중의 동작을 제어하는 플래그 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`MDImportOptionDefault`|삭제 된 레코드를 건너뛰는 기본 동작을 나타냅니다.|  
|`MDImportOptionAll`|모든 메타 데이터를 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllTypeDefs`|는 삭제 된 항목을 포함 하 여 모든 형식 정의를 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllMethodDefs`|는 삭제 된 항목을 포함 하 여 모든 MethodDefs을 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllFieldDefs`|는 삭제 된 항목을 포함 하 여 모든 FieldDefs을 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllProperties`|는 삭제 된 항목을 포함 하 여 모든 PropertyDefs을 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllEvents`|는 삭제 된 항목을 포함 하 여 모든 EventDefs을 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllCustomAttributes`|는 삭제 된 항목을 포함 하 여 모든 사용자 지정 특성을 열거 해야 함을 나타냅니다.|  
|`MDImportOptionAllExportedTypes`|는 삭제 된 형식을 포함 하 여 내보낸 모든 형식을 열거 해야 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
