---
description: '다음에 대 한 자세한 정보: CorLinkerOptions 열거형'
title: CorLinkerOptions 열거형
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: 40f8ba6382fc937a072e01f9b3f6f89056f628db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784433"
---
# <a name="corlinkeroptions-enumeration"></a>CorLinkerOptions 열거형

메타데이터 링커 옵션을 선택하는 플래그를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`MDAssembly`|Private 형식 및 전역 함수는 유지 되지 않습니다.|  
|`MDNetModule`|Private 형식 및 전역 함수는 유지 됩니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
