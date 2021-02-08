---
description: '자세히 알아보기: ICLRStrongName:: StrongNameCompareAssemblies 메서드'
title: ICLRStrongName::StrongNameCompareAssemblies 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: ab02312073f9caf5059ecf7b4eeddaef864bd7b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799653"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="224bc-103">ICLRStrongName::StrongNameCompareAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="224bc-103">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>

<span data-ttu-id="224bc-104">두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-104">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="224bc-105">구문</span><span class="sxs-lookup"><span data-stu-id="224bc-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="224bc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="224bc-106">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="224bc-107">진행 첫 번째 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-107">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="224bc-108">진행 두 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-108">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="224bc-109">제한이 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-109">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="224bc-110">`SN_CMP_DIFFERENT` (0)-어셈블리가 다른 데이터를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-110">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="224bc-111">`SN_CMP_IDENTICAL` (1)-시그니처와 체크섬을 포함 하 여 어셈블리가 정확히 동일 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-111">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="224bc-112">`SN_CMP_SIGONLY` (2)-어셈블리가 시그니처와 체크섬만 다른 것으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-112">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="224bc-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="224bc-113">Return Value</span></span>  

 <span data-ttu-id="224bc-114">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="224bc-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="224bc-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="224bc-115">Requirements</span></span>  

 <span data-ttu-id="224bc-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="224bc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="224bc-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="224bc-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="224bc-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="224bc-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="224bc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="224bc-120">설명</span><span class="sxs-lookup"><span data-stu-id="224bc-120">Remarks</span></span>  

 <span data-ttu-id="224bc-121">어셈블리의 강력한 이름 서명은 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="224bc-121">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="224bc-122">참조</span><span class="sxs-lookup"><span data-stu-id="224bc-122">See also</span></span>

- [<span data-ttu-id="224bc-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="224bc-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
