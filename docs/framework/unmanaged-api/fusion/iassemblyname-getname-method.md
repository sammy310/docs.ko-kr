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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88a46ecadaf2b191e8321c5629bc77b0c67dfd3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079528"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="13046-102">IAssemblyName::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="13046-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="13046-103">이 참조 되는 어셈블리의 간단 하 고 암호화 되지 않은 이름을 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="13046-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13046-104">구문</span><span class="sxs-lookup"><span data-stu-id="13046-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13046-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13046-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="13046-106">[out에서] 크기 `pwzName` 와이드 문자에서 null 종결자 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="13046-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="13046-107">[out] 참조 된 어셈블리의 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="13046-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13046-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13046-108">Requirements</span></span>  
 <span data-ttu-id="13046-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13046-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13046-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="13046-110">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="13046-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="13046-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="13046-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="13046-112">See also</span></span>

- [<span data-ttu-id="13046-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13046-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
