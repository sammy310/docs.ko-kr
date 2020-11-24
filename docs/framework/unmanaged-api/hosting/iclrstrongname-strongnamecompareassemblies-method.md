---
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
ms.openlocfilehash: ddcbe84053aa7f4cafd81e905f8aef988f92875e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685704"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="1d9f3-102">ICLRStrongName::StrongNameCompareAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="1d9f3-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>

<span data-ttu-id="1d9f3-103">두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d9f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d9f3-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d9f3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d9f3-105">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="1d9f3-106">진행 첫 번째 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="1d9f3-107">진행 두 번째 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="1d9f3-108">제한이 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="1d9f3-109">`SN_CMP_DIFFERENT` (0)-어셈블리가 다른 데이터를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="1d9f3-110">`SN_CMP_IDENTICAL` (1)-시그니처와 체크섬을 포함 하 여 어셈블리가 정확히 동일 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="1d9f3-111">`SN_CMP_SIGONLY` (2)-어셈블리가 시그니처와 체크섬만 다른 것으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d9f3-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="1d9f3-112">Return Value</span></span>  

 <span data-ttu-id="1d9f3-113">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="1d9f3-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d9f3-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d9f3-114">Requirements</span></span>  

 <span data-ttu-id="1d9f3-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d9f3-116">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="1d9f3-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1d9f3-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d9f3-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9f3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d9f3-119">설명</span><span class="sxs-lookup"><span data-stu-id="1d9f3-119">Remarks</span></span>  

 <span data-ttu-id="1d9f3-120">어셈블리의 강력한 이름 서명은 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9f3-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9f3-121">참조</span><span class="sxs-lookup"><span data-stu-id="1d9f3-121">See also</span></span>

- [<span data-ttu-id="1d9f3-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d9f3-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
