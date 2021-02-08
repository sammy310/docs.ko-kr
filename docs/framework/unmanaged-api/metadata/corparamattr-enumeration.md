---
description: '다음에 대 한 자세한 정보: CorParamAttr 열거형'
title: CorParamAttr 열거형
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: c07569d3fb92b20a7985dbfeb2205af727866051
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784290"
---
# <a name="corparamattr-enumeration"></a>CorParamAttr 열거형

메서드 매개 변수의 메타데이터를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`pdIn`|매개 변수가 메서드 호출에 전달 되도록 지정 합니다.|  
|`pdOut`|매개 변수가 메서드 반환에서 전달 되도록 지정 합니다.|  
|`pdOptional`|매개 변수를 선택적 요소로 지정합니다.|  
|`pdReservedMask`|공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.|  
|`pdHasDefault`|매개 변수가 기본값을 갖도록 지정합니다.|  
|`pdHasFieldMarshal`|매개 변수에 마샬링 정보를 포함 하도록 지정 합니다.|  
|`pdUnused`|사용되지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
