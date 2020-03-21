---
title: AssemblyComparisonResult 열거형
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178299"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="06d5e-102">AssemblyComparisonResult 열거형</span><span class="sxs-lookup"><span data-stu-id="06d5e-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="06d5e-103">[비교어셈블리 ID](compareassemblyidentity-function.md) 함수에 의해 결정된 대로 두 어셈블리 ID의 동등성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d5e-104">구문</span><span class="sxs-lookup"><span data-stu-id="06d5e-104">Syntax</span></span>  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="06d5e-105">구성원</span><span class="sxs-lookup"><span data-stu-id="06d5e-105">Members</span></span>  
  
|<span data-ttu-id="06d5e-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="06d5e-106">Member name</span></span>|<span data-ttu-id="06d5e-107">Description</span><span class="sxs-lookup"><span data-stu-id="06d5e-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="06d5e-108">비교의 모든 어셈블리 필드가 일치음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="06d5e-109">어셈블리는 .NET Framework 버전 2.0에서 어셈블리 버전 번호의 공통 언어 런타임 버전(CLR) 통합을 기반으로 동등한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="06d5e-110">.NET Framework 2.0에서 어셈블리 버전 번호의 CLR 통합을 기반으로 어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="06d5e-111">어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="06d5e-112">버전 번호의 레거시 통합을 기반으로 어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="06d5e-113">명명된 어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="06d5e-114">어셈블리는 .NET Framework의 레거시 버전에서 버전 번호의 CLR 통합에 따라 동등한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="06d5e-115">버전 번호가 무시된 두 개의 단순히 명명된 어셈블리 간의 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="06d5e-116">두 어셈블리 간에 일치하는 집합이 발생하지 않은 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="06d5e-117">두 어셈블리가 부분적으로만 일치하는 버전 번호를 제외하고 일치한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="06d5e-118">일치하지 않는 버전 번호를 제외하고 두 어셈블리가 일치한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="06d5e-119">비동등성에 대한 이유가 알려져 있지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06d5e-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06d5e-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06d5e-120">Requirements</span></span>  
 <span data-ttu-id="06d5e-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06d5e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d5e-122">**헤더:** 퓨전.h</span><span class="sxs-lookup"><span data-stu-id="06d5e-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="06d5e-123">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="06d5e-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06d5e-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d5e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d5e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06d5e-125">See also</span></span>

- [<span data-ttu-id="06d5e-126">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="06d5e-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="06d5e-127">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="06d5e-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
