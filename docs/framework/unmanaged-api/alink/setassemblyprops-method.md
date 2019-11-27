---
title: SetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
ms.openlocfilehash: 4bfad8b985a8ef059031464e99a8004842b276c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445579"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="de9ee-102">SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="de9ee-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="de9ee-103">어셈블리 수준 속성을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de9ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="de9ee-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="de9ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de9ee-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="de9ee-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="de9ee-107">속성을 정의 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-107">File that defines the property.</span></span> <span data-ttu-id="de9ee-108">`AssemblyID`에서 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="de9ee-109">수정할 옵션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="de9ee-110">옵션의 새 값입니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de9ee-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="de9ee-111">Return Value</span></span>  
 <span data-ttu-id="de9ee-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de9ee-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de9ee-113">Requirements</span></span>  
 <span data-ttu-id="de9ee-114">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="de9ee-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de9ee-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de9ee-115">See also</span></span>

- [<span data-ttu-id="de9ee-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de9ee-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="de9ee-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de9ee-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="de9ee-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="de9ee-118">ALink API</span></span>](index.md)
