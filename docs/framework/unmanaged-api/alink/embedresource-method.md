---
description: '자세히 알아보기: EmbedResource 메서드'
title: EmbedResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: f7896172e7416048352788caf7e092096924b7af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638355"
---
# <a name="embedresource-method"></a><span data-ttu-id="7b3ab-103">EmbedResource 메서드</span><span class="sxs-lookup"><span data-stu-id="7b3ab-103">EmbedResource Method</span></span>

<span data-ttu-id="7b3ab-104">포함 리소스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-104">Declares an embedded resource.</span></span> <span data-ttu-id="7b3ab-105">이 메서드는 실제로 리소스를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-105">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b3ab-106">구문</span><span class="sxs-lookup"><span data-stu-id="7b3ab-106">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b3ab-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b3ab-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="7b3ab-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-108">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7b3ab-109">리소스를 포함 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-109">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="7b3ab-110">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-110">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="7b3ab-111">RVA에서 리소스의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-111">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7b3ab-112">및와 같은 내게 필요한 옵션 플래그 `mrPublic` `mrPrivate` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-112">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="7b3ab-113">이러한 플래그는 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-113">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b3ab-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="7b3ab-114">Return Value</span></span>  

 <span data-ttu-id="7b3ab-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b3ab-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b3ab-116">Requirements</span></span>  

 <span data-ttu-id="7b3ab-117">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b3ab-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3ab-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b3ab-118">See also</span></span>

- [<span data-ttu-id="7b3ab-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b3ab-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7b3ab-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b3ab-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7b3ab-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="7b3ab-121">ALink API</span></span>](index.md)
