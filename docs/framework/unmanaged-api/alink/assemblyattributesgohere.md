---
title: AssemblyAttributesGoHere Class (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHere
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
ms.openlocfilehash: 99d7d2bbbb0586db34b5cb7a785b0448a20ab5bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446646"
---
# <a name="assemblyattributesgohere-class"></a><span data-ttu-id="e6fed-102">AssemblyAttributesGoHere Class</span><span class="sxs-lookup"><span data-stu-id="e6fed-102">AssemblyAttributesGoHere Class</span></span>

<span data-ttu-id="e6fed-103">ALink에서 사용자 지정 특성 정보를 저장하는 자리 표시자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6fed-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6fed-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6fed-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHere
```

## <a name="remarks"></a><span data-ttu-id="e6fed-105">주의</span><span class="sxs-lookup"><span data-stu-id="e6fed-105">Remarks</span></span>

<span data-ttu-id="e6fed-106">이 형식에 대한 참조는 소스에 어셈블리 사용자 지정 특성이 들어 있는 netmodule 내부에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fed-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="e6fed-107">이러한 유형에 대한 참조가 포함된 netmodule 하나 이상에서 어셈블리 매니페스트를 빌드할 때 ALink에서는 이들 참조에 연결된 정보를 사용하여 실제 사용자 지정 특성을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6fed-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="e6fed-108">따라서 이 형식은 인스턴스화되지 않으며, 이에 대한 참조는 빌드 프로세스 부분으로만 사용되고 최종 어셈블리에서 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6fed-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="e6fed-109">이 형식에 대한 참조는 보안과 관련이 없고 다양한 용도로 사용되지 않는 사용자 지정 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6fed-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>

<span data-ttu-id="e6fed-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span><span class="sxs-lookup"><span data-stu-id="e6fed-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6fed-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6fed-111">Requirements</span></span>

<span data-ttu-id="e6fed-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="e6fed-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="e6fed-113">참조</span><span class="sxs-lookup"><span data-stu-id="e6fed-113">See also</span></span>

- [<span data-ttu-id="e6fed-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="e6fed-114">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="e6fed-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="e6fed-115">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="e6fed-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="e6fed-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
