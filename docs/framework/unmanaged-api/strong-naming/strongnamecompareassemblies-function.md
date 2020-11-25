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
ms.openlocfilehash: e7292635ea0344f1c77c8d44908a9a811e464ff9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732309"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="b7787-102">StrongNameCompareAssemblies 함수</span><span class="sxs-lookup"><span data-stu-id="b7787-102">StrongNameCompareAssemblies Function</span></span>

<span data-ttu-id="b7787-103">두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="b7787-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-104">This function has been deprecated.</span></span> <span data-ttu-id="b7787-105">대신 [ICLRStrongName:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7787-106">구문</span><span class="sxs-lookup"><span data-stu-id="b7787-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7787-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7787-107">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="b7787-108">진행 첫 번째 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="b7787-109">진행 두 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="b7787-110">제한이 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="b7787-111">`SN_CMP_DIFFERENT` (0)-어셈블리가 다른 데이터를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="b7787-112">`SN_CMP_IDENTICAL` (1)-시그니처와 체크섬을 포함 하 여 어셈블리가 정확히 동일 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="b7787-113">`SN_CMP_SIGONLY` (2)-어셈블리가 시그니처와 체크섬만 다른 것으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7787-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="b7787-114">Return Value</span></span>  

 <span data-ttu-id="b7787-115">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7787-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7787-116">Requirements</span></span>  

 <span data-ttu-id="b7787-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7787-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7787-118">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="b7787-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b7787-119">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7787-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7787-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7787-121">설명</span><span class="sxs-lookup"><span data-stu-id="b7787-121">Remarks</span></span>  

 <span data-ttu-id="b7787-122">어셈블리의 강력한 이름 서명은 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="b7787-123">`StrongNameCompareAssemblies`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b7787-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7787-124">참조</span><span class="sxs-lookup"><span data-stu-id="b7787-124">See also</span></span>

- [<span data-ttu-id="b7787-125">StrongNameCompareAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="b7787-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="b7787-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7787-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
