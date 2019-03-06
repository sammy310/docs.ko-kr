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
ms.openlocfilehash: 261d80caa43ec478d3a3a33acdebcc1bfcfde8cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500709"
---
# <a name="addimport-method"></a><span data-ttu-id="3c9f7-102">AddImport 메서드</span><span class="sxs-lookup"><span data-stu-id="3c9f7-102">AddImport Method</span></span>
<span data-ttu-id="3c9f7-103">어셈블리에 가져오기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9f7-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c9f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c9f7-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c9f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c9f7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3c9f7-106">확대 하 여 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c9f7-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="3c9f7-107">고유한 ID를 검색할 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)를 가져올 파일의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9f7-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3c9f7-108">COM + FileDef 플래그와 같은 `ffContainsNoMetaData` 고 `ffWriteable`입니다.</span><span class="sxs-lookup"><span data-stu-id="3c9f7-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="3c9f7-109">`dwFlags` 에 전달 됩니다 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9f7-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="3c9f7-110">결과 파일에 대 한 ID를 받는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3c9f7-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c9f7-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="3c9f7-111">Return Value</span></span>  
 <span data-ttu-id="3c9f7-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9f7-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c9f7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c9f7-113">Requirements</span></span>  
 <span data-ttu-id="3c9f7-114">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="3c9f7-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9f7-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c9f7-115">See also</span></span>
- [<span data-ttu-id="3c9f7-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c9f7-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3c9f7-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c9f7-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3c9f7-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="3c9f7-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
