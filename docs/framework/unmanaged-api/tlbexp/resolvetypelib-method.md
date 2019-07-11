---
title: ResolveTypeLib 메서드
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6db8925fb966f4a8b2a213b0d6e340d0edf107
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756424"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="0c6b0-102">ResolveTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="0c6b0-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="0c6b0-103">해당 정규화 된 경로 반환 하 여 형식 라이브러리의 단순한 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c6b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c6b0-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c6b0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c6b0-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="0c6b0-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 형식 라이브러리의 간단한 이름을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="0c6b0-107">[in] 레지스트리에서 형식 라이브러리에 할당 된 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="0c6b0-108">[in] 지역화 ID 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="0c6b0-109">[in] 형식 라이브러리의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="0c6b0-110">예를 들어 버전용 *x.y*, 주 버전 번호는 *x*합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="0c6b0-111">[in] 형식 라이브러리의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="0c6b0-112">버전에 대 한 예를 들어 *x.y*, 부 버전 번호가 *y*합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="0c6b0-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) 운영 환경을 식별 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="0c6b0-114">일반적인 값은 SYS_WIN32 SYS_WIN64입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="0c6b0-115">[out] 에 대 한 포인터를 [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 에 명명 된 형식 라이브러리의 전체 경로 포함 하는 `bstrSimpleName` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c6b0-116">설명</span><span class="sxs-lookup"><span data-stu-id="0c6b0-116">Remarks</span></span>  
 <span data-ttu-id="0c6b0-117">합니다 `ResolveTypeLib` 메서드를 호출 합니다 [LoadTypeLibWithResolver 함수](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) 하는 동안 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="0c6b0-118">이 인터페이스의 사용자 지정 구현을 반환 해야 합니다는 [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 에 명명 된 형식 라이브러리의 전체 경로 포함 하는 `bstrSimpleName` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c6b0-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c6b0-119">Requirements</span></span>  
 <span data-ttu-id="0c6b0-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c6b0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c6b0-121">**헤더:** TlbRef.idl, TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="0c6b0-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="0c6b0-122">**라이브러리:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="0c6b0-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="0c6b0-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c6b0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6b0-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c6b0-124">See also</span></span>

- [<span data-ttu-id="0c6b0-125">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="0c6b0-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="0c6b0-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="0c6b0-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
