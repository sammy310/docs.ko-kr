---
title: IAssemblyName::GetName 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 5f758d76d779cff7db119e69dc1cf3342071f1c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134344"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="09a07-102">IAssemblyName::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="09a07-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="09a07-103">이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리의 단순한 암호화 되지 않은 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09a07-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a07-104">구문</span><span class="sxs-lookup"><span data-stu-id="09a07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09a07-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09a07-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="09a07-106">[in, out] Null 종결자 문자를 포함 하 여 와이드 문자 `pwzName` 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="09a07-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="09a07-107">제한이 참조 된 어셈블리의 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="09a07-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a07-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09a07-108">Requirements</span></span>  
 <span data-ttu-id="09a07-109">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09a07-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09a07-110">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="09a07-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="09a07-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09a07-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a07-112">참조</span><span class="sxs-lookup"><span data-stu-id="09a07-112">See also</span></span>

- [<span data-ttu-id="09a07-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09a07-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
