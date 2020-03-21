---
title: Me, My, MyBase 및 MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401432"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="4d642-102">Visual Basic의 Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="4d642-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="4d642-103">`Me``MyBase`및 `My`Visual `MyClass` Basic의 이름은 비슷하지만 목적은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="4d642-104">이 항목에서는 이러한 엔터티를 구분하기 위해 이러한 각 엔터티에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="4d642-105">본인</span><span class="sxs-lookup"><span data-stu-id="4d642-105">Me</span></span>  
 <span data-ttu-id="4d642-106">키워드는 `Me` 코드가 현재 실행 중인 클래스 또는 구조의 특정 인스턴스를 참조하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="4d642-107">`Me`현재 인스턴스를 참조하는 개체 변수 또는 구조 변수처럼 행동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="4d642-108">사용 `Me` 은 클래스 또는 구조자의 현재 실행 중인 인스턴스에 대한 정보를 다른 클래스, 구조또는 모듈의 프로시저에 전달하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="4d642-109">예를 들어 모듈에 다음 절차가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="4d642-110">다음 문을 사용 하 여이 프로시저를 호출 하 고 인수로 <xref:System.Windows.Forms.Form> 클래스의 현재 인스턴스를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="4d642-111">My</span><span class="sxs-lookup"><span data-stu-id="4d642-111">My</span></span>  
 <span data-ttu-id="4d642-112">이 `My` 기능을 사용하면 여러 .NET Framework 클래스에 쉽고 직관적으로 액세스할 수 있으므로 Visual Basic 사용자가 컴퓨터, 응용 프로그램, 설정, 리소스 등과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="4d642-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="4d642-113">MyBase</span></span>  
 <span data-ttu-id="4d642-114">키워드는 `MyBase` 클래스의 현재 인스턴스의 기본 클래스를 참조하는 개체 변수처럼 행동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="4d642-115">`MyBase`일반적으로 파생 클래스에서 재정의되거나 그림자가 있는 기본 클래스 멤버에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="4d642-116">`MyBase.New`파생 된 클래스 생성자에서 base 클래스 생성자 명시적으로 호출 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="4d642-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="4d642-117">MyClass</span></span>  
 <span data-ttu-id="4d642-118">키워드는 `MyClass` 원래 구현된 클래스의 현재 인스턴스를 참조하는 개체 변수처럼 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="4d642-119">`MyClass``Me`과 비슷하지만 모든 메서드 호출은 메서드가 `NotOverridable`있는 것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d642-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d642-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d642-120">See also</span></span>

- [<span data-ttu-id="4d642-121">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="4d642-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
