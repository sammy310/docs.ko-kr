---
ms.openlocfilehash: bf7ea8a36b9c36d82b4c00ada890829bf4c2c024
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "97700864"
---
### <a name="include-specific-api-surfaces"></a><span data-ttu-id="9c308-101">특정 API 화면 포함</span><span class="sxs-lookup"><span data-stu-id="9c308-101">Include specific API surfaces</span></span>

<span data-ttu-id="9c308-102">액세스 가능성에 따라이 규칙을 실행할 코드 베이스의 부분을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c308-102">You can configure which parts of your codebase to run this rule on, based on their accessibility.</span></span> <span data-ttu-id="9c308-103">예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 *editorconfig* 파일에 다음 키-값 쌍을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c308-103">For example, to specify that the rule should run only against the non-public API surface, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.api_surface = private, internal
```
