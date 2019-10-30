---
title: IAssemblyCache::QueryAssemblyInfo 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
ms.openlocfilehash: e975db68252e866a0bf7898f1c9d3cbe67bbe24f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134573"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a>IAssemblyCache::QueryAssemblyInfo 메서드
지정 된 어셈블리에 대 한 요청 된 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwFlags`  
 진행 Fusion에 정의 된 플래그입니다. 다음 값이 지원 됩니다.  
  
- QUERYASMINFO_FLAG_VALIDATE (0x00000001)  
  
- QUERYASMINFO_FLAG_GETSIZE (0x00000002)  
  
 `pszAssemblyName`  
 진행 데이터가 검색 될 어셈블리의 이름입니다.  
  
 `pAsmInfo`  
 [in, out] 어셈블리에 대 한 데이터를 포함 하는 [ASSEMBLY_INFO](assembly-info-structure.md) 구조체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IAssemblyCache 인터페이스](iassemblycache-interface.md)
