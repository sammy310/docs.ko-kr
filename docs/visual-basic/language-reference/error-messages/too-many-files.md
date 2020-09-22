---
title: 파일이 너무 많습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: cd168ce86569d2d7558e21a5b4cc5ef385b28313
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873551"
---
# <a name="too-many-files"></a><span data-ttu-id="9bcfa-102">파일이 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-102">Too many files</span></span>

<span data-ttu-id="9bcfa-103">운영 체제에서 허용 하는 것 보다 더 많은 파일이 루트 디렉터리에 생성 되었거나 CONFIG.SYS 파일의 **files =** 설정에 지정 된 숫자 보다 많은 파일이 열렸습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9bcfa-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9bcfa-104">To correct this error</span></span>  
  
1. <span data-ttu-id="9bcfa-105">프로그램이 루트 디렉터리에서 파일을 열거나 닫거나 저장 하는 경우 하위 디렉터리를 사용 하도록 프로그램을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="9bcfa-106">CONFIG.SYS 파일에서 **파일 =** 설정에 지정 된 파일 수를 늘리고 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcfa-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bcfa-107">참조</span><span class="sxs-lookup"><span data-stu-id="9bcfa-107">See also</span></span>

- [<span data-ttu-id="9bcfa-108">오류 형식</span><span class="sxs-lookup"><span data-stu-id="9bcfa-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
