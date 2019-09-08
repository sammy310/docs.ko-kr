---
title: AddFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1406c68f1f6abff4d140b131f5f630d0fd767e1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787694"
---
# <a name="addfile-method"></a><span data-ttu-id="e43fb-102">AddFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e43fb-102">AddFile Method</span></span>
<span data-ttu-id="e43fb-103">어셈블리에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-103">Adds files to the assembly.</span></span> <span data-ttu-id="e43fb-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43fb-105">구문</span><span class="sxs-lookup"><span data-stu-id="e43fb-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e43fb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e43fb-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e43fb-107">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="e43fb-108">추가할 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e43fb-109">`ffContainsNoMetaData` 및`ffWriteable`와 같은 com + filedef 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="e43fb-110">`dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="e43fb-111">필요한 경우 메타 데이터를 내보내는 데 사용할 [IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="e43fb-112">추가 된 파일의 고유 ID가 저장 될 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e43fb-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="e43fb-113">Return Value</span></span>  
 <span data-ttu-id="e43fb-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43fb-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e43fb-115">Requirements</span></span>  
 <span data-ttu-id="e43fb-116">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e43fb-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43fb-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="e43fb-117">See also</span></span>

- [<span data-ttu-id="e43fb-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e43fb-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e43fb-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e43fb-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e43fb-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="e43fb-120">ALink API</span></span>](index.md)
