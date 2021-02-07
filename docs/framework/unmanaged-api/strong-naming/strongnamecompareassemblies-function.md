---
description: '자세히 알아보기: StrongNameCompareAssemblies 함수'
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
ms.openlocfilehash: e59bb96a89dc1e1cf8b809c3e0d538aaffe83b8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736546"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="66d3f-103">StrongNameCompareAssemblies 함수</span><span class="sxs-lookup"><span data-stu-id="66d3f-103">StrongNameCompareAssemblies Function</span></span>

<span data-ttu-id="66d3f-104">두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-104">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="66d3f-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-105">This function has been deprecated.</span></span> <span data-ttu-id="66d3f-106">대신 [ICLRStrongName:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-106">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d3f-107">구문</span><span class="sxs-lookup"><span data-stu-id="66d3f-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66d3f-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66d3f-108">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="66d3f-109">진행 첫 번째 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-109">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="66d3f-110">진행 두 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-110">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="66d3f-111">제한이 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-111">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="66d3f-112">`SN_CMP_DIFFERENT` (0)-어셈블리가 다른 데이터를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-112">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="66d3f-113">`SN_CMP_IDENTICAL` (1)-시그니처와 체크섬을 포함 하 여 어셈블리가 정확히 동일 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-113">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="66d3f-114">`SN_CMP_SIGONLY` (2)-어셈블리가 시그니처와 체크섬만 다른 것으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-114">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66d3f-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="66d3f-115">Return Value</span></span>  

 <span data-ttu-id="66d3f-116">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d3f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66d3f-117">Requirements</span></span>  

 <span data-ttu-id="66d3f-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66d3f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d3f-119">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="66d3f-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="66d3f-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66d3f-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d3f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66d3f-122">설명</span><span class="sxs-lookup"><span data-stu-id="66d3f-122">Remarks</span></span>  

 <span data-ttu-id="66d3f-123">어셈블리의 강력한 이름 서명은 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-123">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="66d3f-124">`StrongNameCompareAssemblies`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="66d3f-124">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d3f-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66d3f-125">See also</span></span>

- [<span data-ttu-id="66d3f-126">StrongNameCompareAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="66d3f-126">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="66d3f-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66d3f-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
