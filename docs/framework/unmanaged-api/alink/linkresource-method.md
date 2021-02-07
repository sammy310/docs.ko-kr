---
description: 다음에 대해 자세히 알아보세요. LinkResource 메서드
title: LinkResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: ff12138433577eccbb313b8e64a329be1358ba70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662548"
---
# <a name="linkresource-method"></a><span data-ttu-id="d01e0-103">LinkResource 메서드</span><span class="sxs-lookup"><span data-stu-id="d01e0-103">LinkResource Method</span></span>

<span data-ttu-id="d01e0-104">리소스의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-104">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d01e0-105">구문</span><span class="sxs-lookup"><span data-stu-id="d01e0-105">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d01e0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d01e0-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="d01e0-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-107">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="d01e0-108">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-108">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="d01e0-109">선택적 새 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-109">Optional new file name.</span></span> <span data-ttu-id="d01e0-110">NULL이 아닌 경우 `pszFileName` pszNewLocation에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-110">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="d01e0-111">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-111">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d01e0-112">및와 같은 내게 필요한 옵션 플래그 `mrPublic` `mrPrivate` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-112">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="d01e0-113">이 매개 변수는 [DefineManifestResource 메서드에](../metadata/imetadataassemblyemit-definemanifestresource-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-113">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d01e0-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="d01e0-114">Return Value</span></span>  

 <span data-ttu-id="d01e0-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d01e0-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d01e0-116">Requirements</span></span>  

 <span data-ttu-id="d01e0-117">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01e0-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d01e0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d01e0-118">See also</span></span>

- [<span data-ttu-id="d01e0-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d01e0-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d01e0-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d01e0-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d01e0-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="d01e0-121">ALink API</span></span>](index.md)
