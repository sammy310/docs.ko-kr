---
description: '자세한 정보: ImportTypes 메서드'
title: ImportTypes 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 9a30c735ca2c9ad0f945628c3de1eb1bb56efe2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662626"
---
# <a name="importtypes-method"></a><span data-ttu-id="63331-103">ImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="63331-103">ImportTypes Method</span></span>

<span data-ttu-id="63331-104">[Importfile 메서드](importfile-method.md)를 통해 가져온 각 범위에서 형식의 가져오기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="63331-104">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63331-105">구문</span><span class="sxs-lookup"><span data-stu-id="63331-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="63331-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63331-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="63331-107">가져올 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="63331-107">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="63331-108">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="63331-108">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="63331-109">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="63331-109">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="63331-110">이 범위에 있는 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="63331-110">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="63331-111">선택적으로 [IMetaDataImport 인터페이스](../metadata/imetadataimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="63331-111">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="63331-112">지정 된 범위에서 필요에 따라 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="63331-112">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63331-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="63331-113">Return Value</span></span>  

 <span data-ttu-id="63331-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="63331-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63331-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63331-115">Requirements</span></span>  

 <span data-ttu-id="63331-116">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="63331-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63331-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63331-117">See also</span></span>

- [<span data-ttu-id="63331-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63331-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="63331-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63331-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="63331-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="63331-120">ALink API</span></span>](index.md)
