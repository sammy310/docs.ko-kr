---
title: AddFile2 메서드
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777525"
---
# <a name="addfile2-method"></a><span data-ttu-id="91f0e-102">AddFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="91f0e-102">AddFile2 Method</span></span>
<span data-ttu-id="91f0e-103">어셈블리에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-103">Adds files to the assembly.</span></span> <span data-ttu-id="91f0e-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f0e-105">구문</span><span class="sxs-lookup"><span data-stu-id="91f0e-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="91f0e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91f0e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="91f0e-107">파일이 추가 된 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="91f0e-108">추가할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="91f0e-109">및 `FileDef` 와`ffWriteable`같은 com + 플래그입니다. `ffContainsNoMetaData`</span><span class="sxs-lookup"><span data-stu-id="91f0e-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="91f0e-110">`dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="91f0e-111">[IMetaDataEmit2 인터페이스](../metadata/imetadataemit2-interface.md) 인터페이스에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="91f0e-112">추가 되는 파일에 대 한 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91f0e-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="91f0e-113">Return Value</span></span>  
 <span data-ttu-id="91f0e-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91f0e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91f0e-115">Requirements</span></span>  
 <span data-ttu-id="91f0e-116">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f0e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f0e-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="91f0e-117">See also</span></span>

- [<span data-ttu-id="91f0e-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91f0e-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="91f0e-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91f0e-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="91f0e-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="91f0e-120">ALink API</span></span>](index.md)
