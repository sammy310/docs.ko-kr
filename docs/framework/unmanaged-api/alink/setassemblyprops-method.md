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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e9f51799ea56cb1e5819d708a0e4a8136a94f3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741486"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="f65ab-102">SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f65ab-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="f65ab-103">어셈블리 수준 속성을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f65ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="f65ab-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f65ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f65ab-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f65ab-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f65ab-107">속성을 정의 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-107">File that defines the property.</span></span> <span data-ttu-id="f65ab-108">NULL 일 수 `AssemblyID` 는 바인딩되지 않은 netmodule를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="f65ab-109">수정 하는 옵션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="f65ab-110">옵션의 새 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f65ab-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="f65ab-111">Return Value</span></span>  
 <span data-ttu-id="f65ab-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f65ab-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f65ab-113">Requirements</span></span>  
 <span data-ttu-id="f65ab-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f65ab-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65ab-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="f65ab-115">See also</span></span>

- [<span data-ttu-id="f65ab-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f65ab-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f65ab-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f65ab-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f65ab-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="f65ab-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
