---
title: CompareAssemblyIdentity 함수
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108917"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="80e4b-102">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="80e4b-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="80e4b-103">두 어셈블리 id를 비교 하 여 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80e4b-104">구문</span><span class="sxs-lookup"><span data-stu-id="80e4b-104">Syntax</span></span>  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="80e4b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80e4b-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="80e4b-106">진행 비교할 첫 번째 어셈블리의 텍스트 id입니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="80e4b-107">진행 `pwzAssemblyIdentity1`에 대 한 사용자 지정 통합을 나타내는 부울 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="80e4b-108">진행 비교 하는 두 번째 어셈블리의 텍스트 id입니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="80e4b-109">진행 `pwzAssemblyIdentity2`에 대 한 사용자 지정 통합을 나타내는 부울 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="80e4b-110">제한이 두 어셈블리가 동일한 지 여부를 나타내는 부울 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="80e4b-111">제한이 비교에 대 한 자세한 정보를 포함 하는 [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80e4b-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="80e4b-112">Return Value</span></span>  
 <span data-ttu-id="80e4b-113">`pfEquivalent`는 두 어셈블리가 동일한 지 여부를 나타내는 부울 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="80e4b-114">`pResult`은 `AssemblyComparisonResult` 값 중 하나를 반환 하 여 `pfEquivalent`값에 대 한 보다 자세한 원인을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80e4b-115">주의</span><span class="sxs-lookup"><span data-stu-id="80e4b-115">Remarks</span></span>  
 <span data-ttu-id="80e4b-116">`CompareAssemblyIdentity` `pwzAssemblyIdentity1` 및 `pwzAssemblyIdentity2` 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="80e4b-117">`pfEquivalent`는 다음 조건 중 하나 이상에서 `true`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="80e4b-118">두 어셈블리 id는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="80e4b-119">강력한 이름의 어셈블리의 경우에는 어셈블리 이름, 버전, 공개 키 토큰 및 문화권이 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="80e4b-120">단순한 이름의 어셈블리의 경우에는 어셈블리 이름 및 문화권과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="80e4b-121">두 어셈블리 id는 모두 .NET Framework에서 실행 되는 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="80e4b-122">이 조건은 어셈블리 버전 번호가 일치 하지 않는 경우에도 `true`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="80e4b-123">두 어셈블리는 관리 되는 어셈블리가 아니지만 `fUnified1` 또는 `fUnified2`는 `true`으로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="80e4b-124">`fUnified` 플래그는 강력한 이름의 어셈블리에 대 한 버전 번호 까지의 모든 버전 번호가 강력한 이름의 어셈블리와 동일한 것으로 간주 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="80e4b-125">예를 들어 `pwzAssemblyIndentity1`의 값이 "MyAssembly, version = 3.0.0.0, culture = 중립, publicKeyToken = ..."이 고 `fUnified1` 값이 `true`경우이는 version 0.0.0.0에서 3.0.0.0 모든 버전의 MyAssembly를로 처리 해야 함을 나타냅니다. 상응.</span><span class="sxs-lookup"><span data-stu-id="80e4b-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="80e4b-126">이 경우 `pwzAssemblyIndentity2`가 `pwzAssemblyIndentity1`와 동일한 어셈블리를 참조 하는 경우에는 더 낮은 버전 번호가 있다는 점을 제외 하 고 `pfEquivalent`는 `true`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="80e4b-127">`pwzAssemblyIdentity2`에서 더 높은 버전 번호를 참조 하는 경우 `fUnified2`의 값이 `true`인 경우에만 `pfEquivalent`를 `true`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="80e4b-128">`pResult` 매개 변수는 두 어셈블리가 동일 하거나 동일 하지 않은 것으로 간주 되는 이유에 대 한 특정 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="80e4b-129">자세한 내용은 [AssemblyComparisonResult 열거형](assemblycomparisonresult-enumeration.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80e4b-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80e4b-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80e4b-130">Requirements</span></span>  
 <span data-ttu-id="80e4b-131">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80e4b-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80e4b-132">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="80e4b-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="80e4b-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80e4b-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80e4b-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80e4b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e4b-135">참조</span><span class="sxs-lookup"><span data-stu-id="80e4b-135">See also</span></span>

- [<span data-ttu-id="80e4b-136">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="80e4b-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="80e4b-137">AssemblyComparisonResult 열거형</span><span class="sxs-lookup"><span data-stu-id="80e4b-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
