---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
ms.openlocfilehash: 5671f8cb51210c27dffdedba28b4b145b3fedc55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732556"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a>ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드

[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 대상 프로세스 내에서 디버거가 메타데이터에 대한 메모리 내 업데이트를 처리하는 방법을 구성합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `flags`  
 대상 [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) 프로세스에서 메타 데이터에 대 한 메모리 내 업데이트가 디버거에 표시 되는지 ( `WriteableMetadataUpdateMode::AlwaysShowUpdates` ) 아니면 표시 되지 않는지 ()를 지정 하는 WriteableMetadataUpdateMode 열거형 값입니다 `WriteableMetadataUpdateMode::LegacyCompatPolicy` .  
  
## <a name="remarks"></a>설명  

 대상 프로세스의 메타데이터는 편집하며 계속하기, 프로파일러 또는 <xref:System.Reflection.Emit?displayProperty=nameWithType>에 의해 업데이트될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugProcess7 인터페이스](icordebugprocess7-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
