---
title: StrongNameCompareAssemblies 함수
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3693a42db8e32a4bb7a399f8c930da011130893
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778732"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="a3621-102">StrongNameCompareAssemblies 함수</span><span class="sxs-lookup"><span data-stu-id="a3621-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="a3621-103">두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="a3621-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-104">This function has been deprecated.</span></span> <span data-ttu-id="a3621-105">사용 된 [iclrstrongname:: Strongnamecompareassemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3621-106">구문</span><span class="sxs-lookup"><span data-stu-id="a3621-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3621-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3621-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="a3621-108">[in] 첫 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="a3621-109">[in] 두 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="a3621-110">[out] 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="a3621-111">`SN_CMP_DIFFERENT` (0)-어셈블리에 다른 데이터가 포함 되어 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="a3621-112">`SN_CMP_IDENTICAL` (1)-어셈블리가 정확히 동일한 지, 해당 서명과 체크섬을 포함 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="a3621-113">`SN_CMP_SIGONLY` (2)-는 어셈블리를 서명 및 체크섬에 의해서만 달라 지는 것을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3621-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="a3621-114">Return Value</span></span>  
 <span data-ttu-id="a3621-115">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3621-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3621-116">Requirements</span></span>  
 <span data-ttu-id="a3621-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3621-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3621-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a3621-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a3621-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a3621-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3621-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3621-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3621-121">설명</span><span class="sxs-lookup"><span data-stu-id="a3621-121">Remarks</span></span>  
 <span data-ttu-id="a3621-122">어셈블리의 강력한 이름 시그니처는 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="a3621-123">경우는 `StrongNameCompareAssemblies` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3621-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3621-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3621-124">See also</span></span>

- [<span data-ttu-id="a3621-125">StrongNameCompareAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="a3621-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="a3621-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3621-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
