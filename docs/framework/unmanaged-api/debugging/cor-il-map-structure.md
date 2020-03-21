---
title: COR_IL_MAP 구조체
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179300"
---
# <a name="cor_il_map-structure"></a>COR_IL_MAP 구조체
함수의 상대 오프셋 변경 내용을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`oldOffset`|이전 Microsoft 중간 언어(MSIL)는 함수의 시작 부분을 기준으로 오프셋됩니다.|  
|`newOffset`|함수의 시작 부분을 기준으로 새 MSIL 오프셋입니다.|  
|`fAccurate`|`true`매핑이 정확하다고 알려져 있는 경우; 그렇지 `false`않으면 .|  
  
## <a name="remarks"></a>설명  
 맵의 형식은 다음과 같습니다: 디버거는 수정되지 않은 원래 MSIL 코드 내에서 MSIL 오프셋을 참조한다고 `oldOffset` 가정합니다. 매개 `newOffset` 변수는 계측된 새 코드 내에서 해당 MSIL 오프셋을 나타냅니다.  
  
 스테핑이 제대로 작동하려면 다음 요구 사항을 충족해야 합니다.  
  
- 맵은 오름차순으로 정렬해야 합니다.  
  
- 계측된 MSIL 코드는 순서를 바운지 않아야 합니다.  
  
- 원래 MSIL 코드를 제거하면 안 됩니다.  
  
- 맵에는 프로그램 데이터베이스(PDB) 파일의 모든 시퀀스 지점을 매핑하는 항목이 포함되어야 합니다.  
  
 맵은 누락된 항목을 보간하지 않습니다. 다음 예제에서는 맵과 그 결과를 보여 주며 그 결과를 보여 주습니다.  
  
 지도:  
  
- 0 이전 오프셋, 0 개의 새 오프셋  
  
- 5 이전 오프셋, 10 개의 새 오프셋  
  
- 9 이전 오프셋, 20 개의 새 오프셋  
  
 결과:  
  
- 0, 1, 2, 3 또는 4의 이전 오프셋은 0의 새 오프셋에 매핑됩니다.  
  
- 5, 6, 7 또는 8의 이전 오프셋은 새 오프셋 10에 매핑됩니다.  
  
- 9 이상의 이전 오프셋은 새 오프셋 20에 매핑됩니다.  
  
- 0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9의 새 오프셋이 이전 오프셋 0에 매핑됩니다.  
  
- 10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19의 새 오프셋이 이전 오프셋 5에 매핑됩니다.  
  
- 20 이상의 새 오프셋은 이전 오프셋 9에 매핑됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르데버그.idl, 코르프로프.아이들  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
