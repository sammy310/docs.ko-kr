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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6d8023c7ac6d917c9df40fb18316ddc12df5ec1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190433"
---
# <a name="corilmap-structure"></a>COR_IL_MAP 구조체
함수의 상대 오프셋 변경 내용을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`oldOffset`|이전 Microsoft 중간 언어 (MSIL) 함수의 시작 부분에 상대적으로 오프셋입니다.|  
|`newOffset`|함수 시작을 기준으로 새 MSIL 오프셋입니다.|  
|`fAccurate`|`true` 매핑이; 정확 하 게 하는 경우 그렇지 않으면 `false`합니다.|  
  
## <a name="remarks"></a>설명  
 Map의 형식은 다음과 같습니다. 디버거는 가정 `oldOffset` 원래, 수정 되지 않은 MSIL 코드 내에서 MSIL 오프셋을 나타냅니다. `newOffset` 매개 변수는 새 계측 된 코드 내에서 해당 MSIL 오프셋을 가리킵니다.  
  
 단계별 코드 실행이 제대로 작동 하려면, 다음 요구 사항은 충족 해야 합니다.  
  
-   지도 오름차순 정렬 되어야 합니다.  
  
-   계측 된 MSIL 코드를 다시 정렬할 수 해야 합니다.  
  
-   원래 MSIL 코드를 제거 되어야 합니다.  
  
-   지도는 프로그램 데이터베이스 (PDB) 파일에서 모든 시퀀스 위치를 매핑하는 항목이 포함 되어야 합니다.  
  
 지도 누락 된 항목을 보간하지 않습니다. 다음 예제에서는 지도 및 해당 결과 보여 줍니다.  
  
 매핑하십시오.  
  
-   이전 오프셋 0, 0 새 오프셋  
  
-   이전 오프셋 5, 10 개의 새 오프셋  
  
-   이전 오프셋 9, 20 새 오프셋  
  
 결과:  
  
-   0, 1, 2, 3 또는 4 이전 오프셋 0 새 오프셋에 매핑됩니다.  
  
-   5, 6, 7 또는 8 이전 오프셋 새 오프셋 10으로 매핑됩니다.  
  
-   9 이상 이전 오프셋 20 새 오프셋에 매핑됩니다.  
  
-   새 오프셋 0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9 이전 오프셋 0에 매핑됩니다.  
  
-   10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19 새 오프셋 5 이전 오프셋에 매핑됩니다.  
  
-   20 이상의 새 오프셋을 9 이전 오프셋에 매핑됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
