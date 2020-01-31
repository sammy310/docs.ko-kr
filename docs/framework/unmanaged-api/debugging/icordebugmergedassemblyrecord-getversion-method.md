---
title: ICorDebugMergedAssemblyRecord::GetVersion 메서드
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 8b5995183be7f1c992cf3230e16456cb248eff0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793073"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>ICorDebugMergedAssemblyRecord::GetVersion 메서드
어셈블리의 버전 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pMajor`  
 [out] 주 버전 번호에 대한 포인터입니다.  
  
 `pMinor`  
 [out] 부 버전 번호에 대한 포인터입니다.  
  
 `pBuild`  
 [out] 빌드 번호에 대한 포인터입니다.  
  
 `pRevision`  
 [out] 수정 번호에 대한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 어셈블리 버전 번호에 대한 자세한 내용은 <xref:System.Version> 클래스 항목을 참조하세요.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugMergedAssemblyRecord 인터페이스](icordebugmergedassemblyrecord-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
