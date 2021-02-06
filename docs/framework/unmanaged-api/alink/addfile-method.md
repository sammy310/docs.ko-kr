---
description: '자세히 알아보기: AddFile 메서드'
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
ms.openlocfilehash: 5e1253587298b2c1559c72dced43ec70dc169090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638628"
---
# <a name="addfile-method"></a><span data-ttu-id="44f75-103">AddFile 메서드</span><span class="sxs-lookup"><span data-stu-id="44f75-103">AddFile Method</span></span>

<span data-ttu-id="44f75-104">어셈블리에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-104">Adds files to the assembly.</span></span> <span data-ttu-id="44f75-105">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-105">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f75-106">구문</span><span class="sxs-lookup"><span data-stu-id="44f75-106">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="44f75-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44f75-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="44f75-108">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-108">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="44f75-109">추가할 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-109">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="44f75-110">및와 같은 COM + FileDef 플래그 `ffContainsNoMetaData` `ffWriteable` 입니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-110">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="44f75-111">`dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-111">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="44f75-112">필요한 경우 메타 데이터를 내보내는 데 사용할 [IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-112">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="44f75-113">추가 된 파일의 고유 ID가 저장 될 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-113">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44f75-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="44f75-114">Return Value</span></span>  

 <span data-ttu-id="44f75-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f75-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44f75-116">Requirements</span></span>  

 <span data-ttu-id="44f75-117">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f75-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f75-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44f75-118">See also</span></span>

- [<span data-ttu-id="44f75-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44f75-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="44f75-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44f75-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="44f75-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="44f75-121">ALink API</span></span>](index.md)
