---
title: EmitAssemblyCustomAttribute 메서드
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
ms.openlocfilehash: 2070d1ec2aec80638c20c764eed5086c4a42e0fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676363"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute 메서드

을 호출 하 여 어셈블리 수준 사용자 지정 특성을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `AssemblyID`  
 어셈블리의 ID입니다.  
  
 `FileToken`  
 특성의 파일을 제거 하는 파일입니다. `AssemblyID`가 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.  
  
 `tkType`  
 사용자 지정 특성의 형식입니다.  
  
 `pCustomValue`  
 사용자 지정 값 데이터입니다.  
  
 `cbCustomValue`  
 사용자 지정 값 데이터의 길이입니다.  
  
 `bSecurity`  
 사용자 지정 특성이 어셈블리 서명과 관련 되어 있으면 TRUE입니다.  
  
 `bAllowMulti`  
 여러 특성을 내보내야 하는 경우 TRUE입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink 필요  
  
## <a name="see-also"></a>참조

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
