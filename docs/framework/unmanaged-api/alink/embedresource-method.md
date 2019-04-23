---
title: EmbedResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef7d6272c04c3edab8ef652bcb2759861ff2b982
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129573"
---
# <a name="embedresource-method"></a><span data-ttu-id="40a2d-102">EmbedResource 메서드</span><span class="sxs-lookup"><span data-stu-id="40a2d-102">EmbedResource Method</span></span>
<span data-ttu-id="40a2d-103">포함된 된 리소스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-103">Declares an embedded resource.</span></span> <span data-ttu-id="40a2d-104">이 메서드는 리소스를 실제로 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a2d-105">구문</span><span class="sxs-lookup"><span data-stu-id="40a2d-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="40a2d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40a2d-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="40a2d-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="40a2d-108">파일 리소스를 포함 하는 파일의 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="40a2d-109">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="40a2d-110">RVA에서 리소스의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="40a2d-111">내게 필요한 옵션 플래그와 같은 `mrPublic` 고 `mrPrivate`입니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="40a2d-112">이러한 플래그에 전달 될 수 있습니다 [DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40a2d-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="40a2d-113">Return Value</span></span>  
 <span data-ttu-id="40a2d-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40a2d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40a2d-115">Requirements</span></span>  
 <span data-ttu-id="40a2d-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="40a2d-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a2d-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="40a2d-117">See also</span></span>

- [<span data-ttu-id="40a2d-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40a2d-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="40a2d-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40a2d-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="40a2d-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="40a2d-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
