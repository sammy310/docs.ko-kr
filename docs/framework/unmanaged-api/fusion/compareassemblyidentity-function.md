---
description: '자세히 알아보기: CompareAssemblyIdentity 함수'
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
ms.openlocfilehash: aa55d1ea0b1968ec4e50106139e154e29e159ec7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761215"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="c89b5-103">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="c89b5-103">CompareAssemblyIdentity Function</span></span>

<span data-ttu-id="c89b5-104">두 어셈블리 id를 비교 하 여 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-104">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89b5-105">구문</span><span class="sxs-lookup"><span data-stu-id="c89b5-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c89b5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c89b5-106">Parameters</span></span>  

 `pwzAssemblyIdentity1`  
 <span data-ttu-id="c89b5-107">진행 비교할 첫 번째 어셈블리의 텍스트 id입니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-107">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="c89b5-108">진행 에 대 한 사용자 지정 통합을 나타내는 부울 플래그입니다 `pwzAssemblyIdentity1` .</span><span class="sxs-lookup"><span data-stu-id="c89b5-108">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="c89b5-109">진행 비교 하는 두 번째 어셈블리의 텍스트 id입니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-109">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="c89b5-110">진행 에 대 한 사용자 지정 통합을 나타내는 부울 플래그입니다 `pwzAssemblyIdentity2` .</span><span class="sxs-lookup"><span data-stu-id="c89b5-110">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="c89b5-111">제한이 두 어셈블리가 동일한 지 여부를 나타내는 부울 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-111">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="c89b5-112">제한이 비교에 대 한 자세한 정보를 포함 하는 [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-112">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c89b5-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="c89b5-113">Return Value</span></span>  

 <span data-ttu-id="c89b5-114">`pfEquivalent` 두 어셈블리가 동일한 지 여부를 나타내는 부울 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-114">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="c89b5-115">`pResult` 값 중 하나를 반환 `AssemblyComparisonResult` 하 여 값에 대 한 보다 자세한 원인을 제공 `pfEquivalent` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-115">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c89b5-116">설명</span><span class="sxs-lookup"><span data-stu-id="c89b5-116">Remarks</span></span>  

 <span data-ttu-id="c89b5-117">`CompareAssemblyIdentity` 및가 동일한 지 여부를 확인 `pwzAssemblyIdentity1` `pwzAssemblyIdentity2` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-117">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="c89b5-118">`pfEquivalent` 는 `true` 다음 조건 중 하나 이상에서로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-118">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="c89b5-119">두 어셈블리 id는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-119">The two assembly identities are equivalent.</span></span> <span data-ttu-id="c89b5-120">강력한 이름의 어셈블리의 경우에는 어셈블리 이름, 버전, 공개 키 토큰 및 문화권이 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-120">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="c89b5-121">단순한 이름의 어셈블리의 경우에는 어셈블리 이름 및 문화권과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-121">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="c89b5-122">두 어셈블리 id는 모두 .NET Framework에서 실행 되는 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-122">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="c89b5-123">이 상태 `true` 는 어셈블리 버전 번호가 일치 하지 않는 경우에도 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-123">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="c89b5-124">두 어셈블리가 관리 되는 어셈블리가 아니지만 `fUnified1` 또는 `fUnified2` 로 설정 `true` 된 경우</span><span class="sxs-lookup"><span data-stu-id="c89b5-124">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="c89b5-125">`fUnified`플래그는 강력한 이름의 어셈블리에 대 한 버전 번호 까지의 모든 버전 번호가 강력한 이름의 어셈블리와 동일한 것으로 간주 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-125">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="c89b5-126">예를 들어 값이 `pwzAssemblyIndentity1` "MyAssembly, version = 3.0.0.0, culture = 중립, publicKeyToken = ..."이 고 값이 `fUnified1` 인 경우이는 `true` version 0.0.0.0에서 3.0.0.0 모든 버전의 MyAssembly를 동등한 것으로 처리 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-126">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="c89b5-127">이 경우에서 `pwzAssemblyIndentity2` 와 동일한 어셈블리를 참조 하 `pwzAssemblyIndentity1` 는 경우는 더 낮은 버전 번호가 있다는 점을 제외 하 고 `pfEquivalent` 는로 설정 됩니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="c89b5-127">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="c89b5-128">가 `pwzAssemblyIdentity2` 더 높은 버전 번호를 참조 하는 경우 `pfEquivalent` 는 `true` 의 값이 인 경우에만로 설정 됩니다 `fUnified2` `true` .</span><span class="sxs-lookup"><span data-stu-id="c89b5-128">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="c89b5-129">`pResult`매개 변수에는 두 어셈블리가 동등 하거나 동일 하지 않은 것으로 간주 되는 이유에 대 한 특정 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-129">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="c89b5-130">자세한 내용은 [AssemblyComparisonResult 열거형](assemblycomparisonresult-enumeration.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c89b5-130">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c89b5-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c89b5-131">Requirements</span></span>  

 <span data-ttu-id="c89b5-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c89b5-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c89b5-133">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c89b5-133">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c89b5-134">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89b5-134">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c89b5-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c89b5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89b5-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c89b5-136">See also</span></span>

- [<span data-ttu-id="c89b5-137">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="c89b5-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="c89b5-138">AssemblyComparisonResult 열거형</span><span class="sxs-lookup"><span data-stu-id="c89b5-138">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
