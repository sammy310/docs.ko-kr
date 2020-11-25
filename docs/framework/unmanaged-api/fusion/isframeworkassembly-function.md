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
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728565"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="f025a-102">IsFrameworkAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="f025a-102">IsFrameworkAssembly Function</span></span>

<span data-ttu-id="f025a-103">지정 된 어셈블리가 관리 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f025a-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f025a-104">구문</span><span class="sxs-lookup"><span data-stu-id="f025a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f025a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f025a-105">Parameters</span></span>  

 `pwzAssemblyReference`  
 <span data-ttu-id="f025a-106">진행 확인할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f025a-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="f025a-107">제한이 어셈블리가 관리 되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f025a-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="f025a-108">진행 어셈블리의 고유 id를 포함 하는 정규화 되지 않은 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f025a-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="f025a-109">[in] `pwzFrameworkAssemblyIdentity`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f025a-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f025a-110">설명</span><span class="sxs-lookup"><span data-stu-id="f025a-110">Remarks</span></span>  

 <span data-ttu-id="f025a-111">`pwzAssemblyReference`매개 변수는 어셈블리 이름을 포함 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f025a-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="f025a-112">이 어셈블리가 .NET Framework의 일부인 경우 `pbIsFrameworkAssembly` 매개 변수에 부울 값이 포함 됩니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="f025a-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="f025a-113">명명 된 어셈블리가 .NET Framework의 일부가 아니거나 `pwzAssemblyReference` 매개 변수가 어셈블리의 이름을 지정 하지 않는 경우에는 `pbIsFrameworkAssembly` 부울 값이 포함 됩니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="f025a-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f025a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f025a-114">Requirements</span></span>  

 <span data-ttu-id="f025a-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f025a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f025a-116">참조</span><span class="sxs-lookup"><span data-stu-id="f025a-116">See also</span></span>

- [<span data-ttu-id="f025a-117">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f025a-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
