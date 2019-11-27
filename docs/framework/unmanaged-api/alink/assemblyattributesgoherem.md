---
title: AssemblyAttributesGoHereM 클래스 (System.runtime.compilerservices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
ms.openlocfilehash: 15b9445aa3eabbd14541cfe5481bfb553c8c0347
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446624"
---
# <a name="assemblyattributesgoherem-class"></a><span data-ttu-id="03f87-102">AssemblyAttributesGoHereM 클래스</span><span class="sxs-lookup"><span data-stu-id="03f87-102">AssemblyAttributesGoHereM Class</span></span>

<span data-ttu-id="03f87-103">ALink에서 사용자 지정 특성 정보를 저장하는 자리 표시자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03f87-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="03f87-104">구문</span><span class="sxs-lookup"><span data-stu-id="03f87-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a><span data-ttu-id="03f87-105">주의</span><span class="sxs-lookup"><span data-stu-id="03f87-105">Remarks</span></span>

<span data-ttu-id="03f87-106">이 형식에 대한 참조는 소스에 어셈블리 사용자 지정 특성이 들어 있는 netmodule 내부에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03f87-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="03f87-107">이러한 유형에 대한 참조가 포함된 netmodule 하나 이상에서 어셈블리 매니페스트를 빌드할 때 ALink에서는 이들 참조에 연결된 정보를 사용하여 실제 사용자 지정 특성을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="03f87-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="03f87-108">따라서 이 형식은 인스턴스화되지 않으며, 이에 대한 참조는 빌드 프로세스 부분으로만 사용되고 최종 어셈블리에서 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03f87-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="03f87-109">이 형식에 대한 참조는 보관과 관련되지 않지만 다양한 용도가 있는 사용자 지정 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03f87-109">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>

<span data-ttu-id="03f87-110">이러한 형식은 .NET Framework 내에서 "내부"로 표시 되 고 <xref:System.Runtime.CompilerServices> 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03f87-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="03f87-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03f87-111">Requirements</span></span>

<span data-ttu-id="03f87-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="03f87-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="03f87-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03f87-113">See also</span></span>

- [<span data-ttu-id="03f87-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="03f87-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="03f87-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="03f87-115">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="03f87-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="03f87-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
