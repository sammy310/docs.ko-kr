---
title: AddImport 메서드
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
ms.openlocfilehash: cf73ada36be66edb3fa267d61873ae9acb088a34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717047"
---
# <a name="addimport-method"></a><span data-ttu-id="879bd-102">AddImport 메서드</span><span class="sxs-lookup"><span data-stu-id="879bd-102">AddImport Method</span></span>

<span data-ttu-id="879bd-103">어셈블리에 가져오기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="879bd-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="879bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="879bd-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="879bd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="879bd-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="879bd-106">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="879bd-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="879bd-107">가져올 파일의 [Importfile 메서드에서](importfile-method.md)검색 된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="879bd-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="879bd-108">및와 같은 COM + FileDef 플래그 `ffContainsNoMetaData` `ffWriteable` 입니다.</span><span class="sxs-lookup"><span data-stu-id="879bd-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="879bd-109">`dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="879bd-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="879bd-110">결과 파일에 대 한 ID를 받는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="879bd-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="879bd-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="879bd-111">Return Value</span></span>  

 <span data-ttu-id="879bd-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="879bd-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="879bd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="879bd-113">Requirements</span></span>  

 <span data-ttu-id="879bd-114">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="879bd-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879bd-115">참조</span><span class="sxs-lookup"><span data-stu-id="879bd-115">See also</span></span>

- [<span data-ttu-id="879bd-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="879bd-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="879bd-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="879bd-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="879bd-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="879bd-118">ALink API</span></span>](index.md)
