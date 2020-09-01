---
description: -preferreduilang(C# 컴파일러 옵션)
title: -preferreduilang(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: f68652e910651ab5c4184376d9eb7729303382d9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124853"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="c0e78-103">-preferreduilang(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="c0e78-103">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="c0e78-104">`-preferreduilang` 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지 등의 출력을 표시하는 언어를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e78-104">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0e78-105">구문</span><span class="sxs-lookup"><span data-stu-id="c0e78-105">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="c0e78-106">인수</span><span class="sxs-lookup"><span data-stu-id="c0e78-106">Arguments</span></span>  
 `language`  
 <span data-ttu-id="c0e78-107">컴파일러 출력에 사용할 언어의 [언어 이름](/windows/desktop/Intl/language-names)입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e78-107">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0e78-108">설명</span><span class="sxs-lookup"><span data-stu-id="c0e78-108">Remarks</span></span>  
 <span data-ttu-id="c0e78-109">`-preferreduilang` 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지와 기타 명령줄 출력에 사용할 언어를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e78-109">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="c0e78-110">해당 언어의 언어 팩이 설치되지 않은 경우 운영 체제의 언어 설정이 대신 사용되고 오류가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e78-110">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="c0e78-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0e78-111">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e78-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0e78-112">See also</span></span>

- [<span data-ttu-id="c0e78-113">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="c0e78-113">C# Compiler Options</span></span>](./index.md)
