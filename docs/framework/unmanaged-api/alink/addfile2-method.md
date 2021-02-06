---
description: '자세히 알아보기: AddFile2 메서드'
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
ms.openlocfilehash: d53527ecf7e8b3a99a11ea99512fbc812125de3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638615"
---
# <a name="addfile2-method"></a><span data-ttu-id="6f539-103">AddFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="6f539-103">AddFile2 Method</span></span>

<span data-ttu-id="6f539-104">어셈블리에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-104">Adds files to the assembly.</span></span> <span data-ttu-id="6f539-105">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-105">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f539-106">구문</span><span class="sxs-lookup"><span data-stu-id="6f539-106">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f539-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f539-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="6f539-108">파일이 추가 된 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-108">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="6f539-109">추가할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-109">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6f539-110">`FileDef`및와 같은 COM + 플래그 `ffContainsNoMetaData` `ffWriteable` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-110">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="6f539-111">`dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-111">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="6f539-112">[IMetaDataEmit2 인터페이스](../metadata/imetadataemit2-interface.md) 인터페이스에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-112">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="6f539-113">추가 되는 파일에 대 한 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-113">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f539-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="6f539-114">Return Value</span></span>  

 <span data-ttu-id="6f539-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f539-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f539-116">Requirements</span></span>  

 <span data-ttu-id="6f539-117">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f539-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f539-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f539-118">See also</span></span>

- [<span data-ttu-id="6f539-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f539-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6f539-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f539-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6f539-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="6f539-121">ALink API</span></span>](index.md)
