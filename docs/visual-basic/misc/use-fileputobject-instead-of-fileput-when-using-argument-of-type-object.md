---
title: "'Object' 형식의 인수를 사용하는 경우 'FilePut' 대신 'FilePutObject'를 사용하세요."
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: c6ae755ad3eca4b1c50b83049885b6cf66f13c07
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100336"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="79df3-102">'Object' 형식의 인수를 사용하는 경우 'FilePut' 대신 'FilePutObject'를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="79df3-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>

<span data-ttu-id="79df3-103">`FilePut` 메서드는 `Object`형식의 인수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79df3-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="79df3-104">모호성을 피하기 위해`FilePutObject` 대신 `FilePut` 를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79df3-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79df3-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="79df3-105">To correct this error</span></span>  
  
- <span data-ttu-id="79df3-106">`FilePut`을 `FilePutObject`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="79df3-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="79df3-107">`Object` 인수를 더 구체적인 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="79df3-107">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="79df3-108">`My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79df3-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79df3-109">참조</span><span class="sxs-lookup"><span data-stu-id="79df3-109">See also</span></span>

- [<span data-ttu-id="79df3-110">My.user. 컴퓨터 파일 시스템</span><span class="sxs-lookup"><span data-stu-id="79df3-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="79df3-111">My.computer. WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="79df3-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
