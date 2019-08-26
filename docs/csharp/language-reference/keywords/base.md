---
title: base 키워드 - C# 참조
ms.custom: seodec18
description: C#의 파생 클래스 내에서 기본 클래스의 멤버에 액세스하는 데 사용되는 base 키워드에 대해 알아봅니다.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: b882a8d1e5979ac184d184be379dd76f7bf3600f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602264"
---
# <a name="base-c-reference"></a><span data-ttu-id="65b3f-103">base(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="65b3f-103">base (C# Reference)</span></span>

<span data-ttu-id="65b3f-104">`base` 키워드는 파생 클래스 내에서 기본 클래스의 멤버에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="65b3f-105">다른 메서드에 의해 재정의된 기본 클래스에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="65b3f-106">파생 클래스의 인스턴스를 만들 때 호출해야 하는 기본 클래스 생성자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="65b3f-107">기본 클래스 액세스는 생성자, 인스턴스 메서드 또는 인스턴스 속성 접근자에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="65b3f-108">정적 메서드 내에서 `base` 키워드를 사용하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="65b3f-109">액세스된 기본 클래스는 클래스 선언에 지정된 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="65b3f-110">예를 들어 `class ClassB : ClassA`를 지정할 경우 ClassA의 기본 클래스에 관계없이 ClassA의 멤버는 ClassB에서 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="65b3f-111">예</span><span class="sxs-lookup"><span data-stu-id="65b3f-111">Example</span></span>

<span data-ttu-id="65b3f-112">이 예제에서 기본 클래스 `Person` 및 파생 클래스 `Employee`에는 둘 다 `Getinfo` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="65b3f-113">`base` 키워드를 사용하면 파생 클래스 내에서 기본 클래스에 대해 `Getinfo` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="65b3f-114">추가 예제는 [new](new-modifier.md), [virtual](virtual.md) 및 [override](override.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65b3f-114">For additional examples, see [new](new-modifier.md), [virtual](virtual.md), and [override](override.md).</span></span>

## <a name="example"></a><span data-ttu-id="65b3f-115">예</span><span class="sxs-lookup"><span data-stu-id="65b3f-115">Example</span></span>

<span data-ttu-id="65b3f-116">이 예제에서는 파생 클래스의 인스턴스를 만들 때 호출되는 기본 클래스 생성자를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65b3f-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="65b3f-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="65b3f-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="65b3f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65b3f-118">See also</span></span>

- [<span data-ttu-id="65b3f-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="65b3f-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="65b3f-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="65b3f-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="65b3f-121">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="65b3f-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="65b3f-122">this</span><span class="sxs-lookup"><span data-stu-id="65b3f-122">this</span></span>](./this.md)
