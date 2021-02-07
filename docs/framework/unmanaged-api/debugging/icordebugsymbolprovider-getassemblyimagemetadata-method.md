---
description: '자세히 알아보기: ICorDebugSymbolProvider:: GetAssemblyImageMetadata 메서드'
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 4abe5cc2b2a31f89e6ca4f8fc643f26eac276515
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717188"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a>ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드

병합된 어셈블리에서 메타데이터를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppMemoryBuffer`  
 제한이 병합 된 어셈블리의 메타 데이터 크기와 주소에 대 한 정보를 포함 하는 [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugSymbolProvider 인터페이스](icordebugsymbolprovider-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
