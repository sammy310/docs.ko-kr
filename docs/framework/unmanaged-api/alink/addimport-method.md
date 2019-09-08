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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787660"
---
# <a name="addimport-method"></a><span data-ttu-id="ae6f0-102">AddImport 메서드</span><span class="sxs-lookup"><span data-stu-id="ae6f0-102">AddImport Method</span></span>
<span data-ttu-id="ae6f0-103">어셈블리에 가져오기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6f0-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae6f0-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae6f0-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae6f0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae6f0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ae6f0-106">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae6f0-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="ae6f0-107">가져올 파일의 [Importfile 메서드에서](importfile-method.md)검색 된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae6f0-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ae6f0-108">`ffContainsNoMetaData` 및`ffWriteable`와 같은 com + filedef 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ae6f0-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="ae6f0-109">`dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae6f0-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="ae6f0-110">결과 파일에 대 한 ID를 받는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae6f0-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae6f0-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="ae6f0-111">Return Value</span></span>  
 <span data-ttu-id="ae6f0-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae6f0-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae6f0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae6f0-113">Requirements</span></span>  
 <span data-ttu-id="ae6f0-114">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="ae6f0-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae6f0-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae6f0-115">See also</span></span>

- [<span data-ttu-id="ae6f0-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae6f0-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ae6f0-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae6f0-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ae6f0-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="ae6f0-118">ALink API</span></span>](index.md)
