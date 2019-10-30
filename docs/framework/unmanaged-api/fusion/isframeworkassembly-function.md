---
title: IsFrameworkAssembly 함수
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123064"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="46757-102">IsFrameworkAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="46757-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="46757-103">지정 된 어셈블리가 관리 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46757-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46757-104">구문</span><span class="sxs-lookup"><span data-stu-id="46757-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="46757-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46757-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="46757-106">진행 확인할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46757-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="46757-107">제한이 어셈블리가 관리 되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="46757-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="46757-108">진행 어셈블리의 고유 id를 포함 하는 정규화 되지 않은 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="46757-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="46757-109">[in] `pwzFrameworkAssemblyIdentity`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="46757-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46757-110">주의</span><span class="sxs-lookup"><span data-stu-id="46757-110">Remarks</span></span>  
 <span data-ttu-id="46757-111">`pwzAssemblyReference` 매개 변수는 어셈블리 이름을 포함 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46757-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="46757-112">이 어셈블리가 .NET Framework의 일부인 경우 `pbIsFrameworkAssembly` 매개 변수에 `true`부울 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46757-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="46757-113">명명 된 어셈블리가 .NET Framework의 일부가 아니거나 `pwzAssemblyReference` 매개 변수가 어셈블리의 이름을 지정 하지 않으면 `pbIsFrameworkAssembly`에 부울 값 `false`포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46757-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46757-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46757-114">Requirements</span></span>  
 <span data-ttu-id="46757-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46757-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46757-116">참조</span><span class="sxs-lookup"><span data-stu-id="46757-116">See also</span></span>

- [<span data-ttu-id="46757-117">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="46757-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
