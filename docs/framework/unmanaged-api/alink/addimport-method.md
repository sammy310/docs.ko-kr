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
ms.openlocfilehash: bbe8a43f44d59249abc713c95fce31f1fb9a5993
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148670"
---
# <a name="addimport-method"></a><span data-ttu-id="15398-102">AddImport 메서드</span><span class="sxs-lookup"><span data-stu-id="15398-102">AddImport Method</span></span>
<span data-ttu-id="15398-103">어셈블리에 가져오기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="15398-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15398-104">구문</span><span class="sxs-lookup"><span data-stu-id="15398-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="15398-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15398-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="15398-106">확대 하 여 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15398-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="15398-107">고유한 ID를 검색할 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)를 가져올 파일의 합니다.</span><span class="sxs-lookup"><span data-stu-id="15398-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="15398-108">COM + FileDef 플래그와 같은 `ffContainsNoMetaData` 고 `ffWriteable`입니다.</span><span class="sxs-lookup"><span data-stu-id="15398-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> `dwFlags` <span data-ttu-id="15398-109">에 전달 됩니다 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15398-109">is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="15398-110">결과 파일에 대 한 ID를 받는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15398-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15398-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="15398-111">Return Value</span></span>  
 <span data-ttu-id="15398-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15398-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15398-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15398-113">Requirements</span></span>  
 <span data-ttu-id="15398-114">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="15398-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15398-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="15398-115">See also</span></span>

- [<span data-ttu-id="15398-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15398-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="15398-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15398-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="15398-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="15398-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
