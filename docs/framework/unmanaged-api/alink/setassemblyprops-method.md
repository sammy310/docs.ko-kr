---
description: '자세한 정보: SetAssemblyProps 메서드'
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
ms.openlocfilehash: 212d8aad22ac1cb231db46f20ff65de2339a21aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662353"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="8d071-103">SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="8d071-103">SetAssemblyProps Method</span></span>

<span data-ttu-id="8d071-104">어셈블리 수준 속성을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-104">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d071-105">구문</span><span class="sxs-lookup"><span data-stu-id="8d071-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d071-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d071-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="8d071-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="8d071-108">속성을 정의 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-108">File that defines the property.</span></span> <span data-ttu-id="8d071-109">`AssemblyID`가 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-109">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="8d071-110">수정할 옵션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-110">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="8d071-111">옵션의 새 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-111">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d071-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="8d071-112">Return Value</span></span>  

 <span data-ttu-id="8d071-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d071-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d071-114">Requirements</span></span>  

 <span data-ttu-id="8d071-115">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d071-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d071-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d071-116">See also</span></span>

- [<span data-ttu-id="8d071-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d071-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8d071-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d071-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8d071-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="8d071-119">ALink API</span></span>](index.md)
