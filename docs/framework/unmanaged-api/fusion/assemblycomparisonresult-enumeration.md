---
description: '자세히 알아보기: AssemblyComparisonResult 열거형'
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
ms.openlocfilehash: 093cff830aa87d28ee86ecaeb6965887279a72d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761290"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="ba546-103">AssemblyComparisonResult 열거형</span><span class="sxs-lookup"><span data-stu-id="ba546-103">AssemblyComparisonResult Enumeration</span></span>

<span data-ttu-id="ba546-104">[CompareAssemblyIdentity](compareassemblyidentity-function.md) 함수에 의해 결정 된 두 어셈블리 id의 동일성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-104">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba546-105">구문</span><span class="sxs-lookup"><span data-stu-id="ba546-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ba546-106">구성원</span><span class="sxs-lookup"><span data-stu-id="ba546-106">Members</span></span>  
  
|<span data-ttu-id="ba546-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="ba546-107">Member name</span></span>|<span data-ttu-id="ba546-108">설명</span><span class="sxs-lookup"><span data-stu-id="ba546-108">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="ba546-109">비교의 모든 어셈블리 필드가 일치 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-109">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="ba546-110">.NET Framework 버전 2.0에서 어셈블리 버전 번호의 CLR (공용 언어 런타임 버전) 통합에 따라 어셈블리가 동일한 것으로 간주 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-110">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="ba546-111">.NET Framework 2.0에서 어셈블리 버전 번호의 CLR 통합을 기반으로 하는 어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-111">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="ba546-112">어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-112">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="ba546-113">버전 번호의 레거시 통합을 기반으로 하는 어셈블리의 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-113">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="ba546-114">단순한 이름의 어셈블리에 대 한 부분 일치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-114">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="ba546-115">는 .NET Framework의 레거시 버전에서 버전 번호의 CLR 통합에 따라 어셈블리가 동일한 것으로 간주 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-115">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="ba546-116">버전 번호가 무시 된 두 개의 단순한 명명 된 어셈블리 사이에 일치 하는 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-116">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="ba546-117">두 어셈블리 사이에 일치 하는 항목이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-117">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="ba546-118">는 부분적 으로만 일치 하는 버전 번호를 제외 하 고 두 어셈블리가 일치 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-118">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="ba546-119">일치 하지 않는 버전 번호를 제외 하 고 두 어셈블리가 일치 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-119">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="ba546-120">같지 않음의 원인을 알 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-120">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba546-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba546-121">Requirements</span></span>  

 <span data-ttu-id="ba546-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba546-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba546-123">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ba546-123">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ba546-124">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba546-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba546-125">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba546-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba546-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba546-126">See also</span></span>

- [<span data-ttu-id="ba546-127">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="ba546-127">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="ba546-128">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="ba546-128">Fusion Enumerations</span></span>](fusion-enumerations.md)
