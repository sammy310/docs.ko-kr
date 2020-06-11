---
title: XML 파일 처리 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: 1e3d96f9398f2c08ed715111f01987e2d1948439
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287261"
---
# <a name="process-the-xml-file-c-programming-guide"></a><span data-ttu-id="ac88d-102">XML 파일 처리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ac88d-102">Process the XML file (C# programming guide)</span></span>

<span data-ttu-id="ac88d-103">컴파일러는 문서 생성을 위해 태그가 지정되는 코드의 각 구문에 대해 ID 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-103">The compiler generates an ID string for each construct in your code that's tagged to generate documentation.</span></span> <span data-ttu-id="ac88d-104">코드에 태그를 지정하는 방법에 대한 자세한 내용은 [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)를 참조하세요. ID 문자열은 구문을 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-104">(For information about how to tag your code, see [Recommended Tags for Documentation Comments](./recommended-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="ac88d-105">XML 파일을 처리하는 프로그램은 ID 문자열을 사용하여 문서가 적용되는 해당 .NET 메타데이터 또는 리플렉션 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-105">Programs that process the XML file can use the ID string to identify the corresponding .NET metadata or reflection item that the documentation applies to.</span></span>

## <a name="id-strings"></a><span data-ttu-id="ac88d-106">ID 문자열</span><span class="sxs-lookup"><span data-stu-id="ac88d-106">ID strings</span></span>

<span data-ttu-id="ac88d-107">XML 파일은 코드의 계층적 표현이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-107">The XML file is not a hierarchical representation of your code.</span></span> <span data-ttu-id="ac88d-108">각 요소에 대해 생성된 ID가 포함된 단순 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-108">It's a flat list that has a generated ID for each element.</span></span>

<span data-ttu-id="ac88d-109">컴파일러는 ID 문자열을 생성할 때 다음 규칙을 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-109">The compiler observes the following rules when it generates the ID strings:</span></span>

- <span data-ttu-id="ac88d-110">문자열에 공백이 없음.</span><span class="sxs-lookup"><span data-stu-id="ac88d-110">No white space is in the string.</span></span>

- <span data-ttu-id="ac88d-111">문자열의 첫 부분이 뒤에 콜론이 붙은 한 글자를 사용해 멤버의 종류를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-111">The first part of the string identifies the kind of member using a single character followed by a colon.</span></span> <span data-ttu-id="ac88d-112">사용되는 멤버 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-112">The following member types are used:</span></span>

    |<span data-ttu-id="ac88d-113">문자</span><span class="sxs-lookup"><span data-stu-id="ac88d-113">Character</span></span>|<span data-ttu-id="ac88d-114">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="ac88d-114">Member type</span></span>|<span data-ttu-id="ac88d-115">참고</span><span class="sxs-lookup"><span data-stu-id="ac88d-115">Notes</span></span>|
    |---------------|-----------------|-|
    |<span data-ttu-id="ac88d-116">N</span><span class="sxs-lookup"><span data-stu-id="ac88d-116">N</span></span>|<span data-ttu-id="ac88d-117">namespace</span><span class="sxs-lookup"><span data-stu-id="ac88d-117">namespace</span></span>|<span data-ttu-id="ac88d-118">네임스페이스에 문서 주석을 추가할 수는 없지만 지원되는 경우 문서 주석에 대한 cref 참조를 만들 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-118">You cannot add documentation comments to a namespace, but you can make cref references to them, where supported.</span></span>|
    |<span data-ttu-id="ac88d-119">T</span><span class="sxs-lookup"><span data-stu-id="ac88d-119">T</span></span>|<span data-ttu-id="ac88d-120">type</span><span class="sxs-lookup"><span data-stu-id="ac88d-120">type</span></span>|<span data-ttu-id="ac88d-121">클래스, 인터페이스, 구조체, 열거형 또는 대리자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-121">A type can be a class, interface, struct, enum, or delegate.</span></span>|
    |<span data-ttu-id="ac88d-122">F</span><span class="sxs-lookup"><span data-stu-id="ac88d-122">F</span></span>|<span data-ttu-id="ac88d-123">필드(field)</span><span class="sxs-lookup"><span data-stu-id="ac88d-123">field</span></span>|
    |<span data-ttu-id="ac88d-124">P</span><span class="sxs-lookup"><span data-stu-id="ac88d-124">P</span></span>|<span data-ttu-id="ac88d-125">속성(property)</span><span class="sxs-lookup"><span data-stu-id="ac88d-125">property</span></span>|<span data-ttu-id="ac88d-126">인덱서 또는 기타 인덱싱된 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-126">Includes indexers or other indexed properties.</span></span>|
    |<span data-ttu-id="ac88d-127">M</span><span class="sxs-lookup"><span data-stu-id="ac88d-127">M</span></span>|<span data-ttu-id="ac88d-128">메서드</span><span class="sxs-lookup"><span data-stu-id="ac88d-128">method</span></span>|<span data-ttu-id="ac88d-129">생성자 및 연산자와 같은 특수 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-129">Includes special methods, such as constructors and operators.</span></span>|
    |<span data-ttu-id="ac88d-130">E</span><span class="sxs-lookup"><span data-stu-id="ac88d-130">E</span></span>|<span data-ttu-id="ac88d-131">event</span><span class="sxs-lookup"><span data-stu-id="ac88d-131">event</span></span>|
    |<span data-ttu-id="ac88d-132">!</span><span class="sxs-lookup"><span data-stu-id="ac88d-132">!</span></span>|<span data-ttu-id="ac88d-133">오류 문자열</span><span class="sxs-lookup"><span data-stu-id="ac88d-133">error string</span></span>|<span data-ttu-id="ac88d-134">문자열의 나머지 부분은 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-134">The rest of the string provides information about the error.</span></span> <span data-ttu-id="ac88d-135">C# 컴파일러는 확인할 수 없는 링크에 대해 오류 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-135">The C# compiler generates error information for links that cannot be resolved.</span></span>|

- <span data-ttu-id="ac88d-136">문자열의 두 번째 부분은 네임스페이스의 루트부터 시작되는 항목의 정규화된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-136">The second part of the string is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="ac88d-137">항목의 이름과 바깥쪽 형식 및 네임스페이스는 마침표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-137">The name of the item, its enclosing type(s), and namespace are separated by periods.</span></span> <span data-ttu-id="ac88d-138">항목 자체의 이름에 마침표가 있으면 이러한 요소를 구분하는 마침표가 해시 기호('#')로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-138">If the name of the item itself has periods, they are replaced by the hash-sign ('#').</span></span> <span data-ttu-id="ac88d-139">항목 이름에는 해시 기호가 직접적으로 포함되지 않는다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-139">It's assumed that no item has a hash-sign directly in its name.</span></span> <span data-ttu-id="ac88d-140">예를 들어 String 생성자의 정규화된 이름은 “System.String.#ctor”입니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-140">For example, the fully qualified name of the String constructor is "System.String.#ctor".</span></span>

- <span data-ttu-id="ac88d-141">속성 및 메서드의 경우 괄호로 묶은 매개 변수 목록이 뒤에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-141">For properties and methods, the parameter list enclosed in parentheses follows.</span></span> <span data-ttu-id="ac88d-142">매개 변수가 없으면 괄호도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-142">If there are no parameters, no parentheses are present.</span></span> <span data-ttu-id="ac88d-143">매개 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-143">The parameters are separated by commas.</span></span> <span data-ttu-id="ac88d-144">각 매개 변수의 인코딩은 .NET 시그니처에서 매개 변수가 인코딩되는 방식을 그대로 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-144">The encoding of each parameter follows directly how it's encoded in a .NET signature:</span></span>

  - <span data-ttu-id="ac88d-145">기본 형식.</span><span class="sxs-lookup"><span data-stu-id="ac88d-145">Base types.</span></span> <span data-ttu-id="ac88d-146">일반 형식(ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE)은 해당 형식의 정규화된 이름으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-146">Regular types (ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE) are represented as the fully qualified name of the type.</span></span>

  - <span data-ttu-id="ac88d-147">내장 형식(예: ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF 및 ELEMENT_TYPE_VOID)은 해당 전체 형식의 정규화된 이름으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-147">Intrinsic types (for example, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF, and ELEMENT_TYPE_VOID) are represented as the fully qualified name of the corresponding full type.</span></span> <span data-ttu-id="ac88d-148">예를 들면 System.Int32 또는 System.TypedReference와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-148">For example, System.Int32 or System.TypedReference.</span></span>

  - <span data-ttu-id="ac88d-149">ELEMENT_TYPE_PTR은 수정된 형식 뒤에 ‘\*’로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-149">ELEMENT_TYPE_PTR is represented as a '\*' following the modified type.</span></span>

  - <span data-ttu-id="ac88d-150">ELEMENT_TYPE_BYREF는 수정된 형식 뒤에 ‘\@’으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-150">ELEMENT_TYPE_BYREF is represented as a '\@' following the modified type.</span></span>

  - <span data-ttu-id="ac88d-151">ELEMENT_TYPE_PINNED는 수정된 형식 뒤에 '^'로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-151">ELEMENT_TYPE_PINNED is represented as a '^' following the modified type.</span></span> <span data-ttu-id="ac88d-152">C# 컴파일러에서는 이 인수가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-152">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="ac88d-153">ELEMENT_TYPE_CMOD_REQ는 수정된 형식 뒤에 '&#124;' 및 한정자 클래스의 정규화된 이름으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-153">ELEMENT_TYPE_CMOD_REQ is represented as a '&#124;' and the fully qualified name of the modifier class, following the modified type.</span></span> <span data-ttu-id="ac88d-154">C# 컴파일러에서는 이 인수가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-154">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="ac88d-155">ELEMENT_TYPE_CMOD_OPT는 수정된 형식 뒤에 '!' 및 한정자 클래스의 정규화된 이름으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-155">ELEMENT_TYPE_CMOD_OPT is represented as a '!' and the fully qualified name of the modifier class, following the modified type.</span></span>

  - <span data-ttu-id="ac88d-156">ELEMENT_TYPE_SZARRAY는 배열의 요소 형식 뒤에 "[]"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-156">ELEMENT_TYPE_SZARRAY is represented as "[]" following the element type of the array.</span></span>

  - <span data-ttu-id="ac88d-157">ELEMENT_TYPE_GENERICARRAY는 배열의 요소 형식 뒤에 "[?]"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-157">ELEMENT_TYPE_GENERICARRAY is represented as "[?]" following the element type of the array.</span></span> <span data-ttu-id="ac88d-158">C# 컴파일러에서는 이 인수가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-158">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="ac88d-159">ELEMENT_TYPE_ARRAY는 [*lowerbound*:`size`,*lowerbound*:`size`]로 표시됩니다. 여기서 쉼표 수는 순위 - 1에 해당하는 값이고, 각 차원의 하한과 크기(확인된 경우)는 10진수로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-159">ELEMENT_TYPE_ARRAY is represented as [*lowerbound*:`size`,*lowerbound*:`size`] where the number of commas is the rank - 1, and the lower bounds and size of each dimension, if known, are represented in decimal.</span></span> <span data-ttu-id="ac88d-160">하한이나 크기가 지정되지 않은 경우에는 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-160">If a lower bound or size is not specified, it's omitted.</span></span> <span data-ttu-id="ac88d-161">특정 차원의 하한과 크기를 생략하면 ':'도 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-161">If the lower bound and size for a particular dimension are omitted, the ':' is omitted as well.</span></span> <span data-ttu-id="ac88d-162">예를 들어 하한이 1이고 크기가 지정되지 않은 2차원 배열은 [1:,1:]로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-162">For example, a 2-dimensional array with 1 as the lower bounds and unspecified sizes is [1:,1:].</span></span>

  - <span data-ttu-id="ac88d-163">ELEMENT_TYPE_FNPTR은 "=FUNC:`type`(*signature*)"로 표시됩니다. 여기서 `type`은 반환 형식이고 *signature*는 메서드의 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-163">ELEMENT_TYPE_FNPTR is represented as "=FUNC:`type`(*signature*)", where `type` is the return type, and *signature* is the arguments of the method.</span></span> <span data-ttu-id="ac88d-164">인수가 없으면 괄호는 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-164">If there are no arguments, the parentheses are omitted.</span></span> <span data-ttu-id="ac88d-165">C# 컴파일러에서는 이 인수가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-165">The C# compiler never generates this.</span></span>

  <span data-ttu-id="ac88d-166">다음 시그니처 구성 요소는 오버로드된 메서드를 구분하는 데 사용되지 않으므로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-166">The following signature components aren't represented because they aren't used to differentiate overloaded methods:</span></span>

  - <span data-ttu-id="ac88d-167">호출 규칙</span><span class="sxs-lookup"><span data-stu-id="ac88d-167">calling convention</span></span>

  - <span data-ttu-id="ac88d-168">반환 형식</span><span class="sxs-lookup"><span data-stu-id="ac88d-168">return type</span></span>

  - <span data-ttu-id="ac88d-169">ELEMENT_TYPE_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="ac88d-169">ELEMENT_TYPE_SENTINEL</span></span>

- <span data-ttu-id="ac88d-170">변환 연산자(`op_Implicit` 및 `op_Explicit`)에 한해 메서드의 반환 값은 뒤에 반환 형식이 붙은 ‘~’로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-170">For conversion operators only (`op_Implicit` and `op_Explicit`), the return value of the method is encoded as a '~' followed by the return type.</span></span>

- <span data-ttu-id="ac88d-171">제네릭 형식의 경우에는 형식 이름 뒤에 억음 악센트 기호와 제네릭 형식 매개 변수의 수를 나타내는 숫자가 차례로 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-171">For generic types, the name of the type is followed by a backtick and then a number that indicates the number of generic type parameters.</span></span> <span data-ttu-id="ac88d-172">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="ac88d-172">For example:</span></span>

     <span data-ttu-id="ac88d-173">``<member name="T:SampleClass`2">``는 `public class SampleClass<T, U>`로 정의된 형식의 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-173">``<member name="T:SampleClass`2">`` is the tag for a type that is defined as `public class SampleClass<T, U>`.</span></span>

     <span data-ttu-id="ac88d-174">제네릭 형식을 매개 변수로 사용하는 메서드의 경우 제네릭 형식 매개 변수는 \`0,\`1과 같이 앞에 억음 악센트 기호가 붙은 숫자로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-174">For methods that take generic types as parameters, the generic type parameters are specified as numbers prefaced with backticks (for example \`0,\`1).</span></span> <span data-ttu-id="ac88d-175">각 숫자는 해당 형식의 제네릭 매개 변수에 대한 0부터 시작되는 배열 표기법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-175">Each number represents a zero-based array notation for the type's generic parameters.</span></span>

## <a name="examples"></a><span data-ttu-id="ac88d-176">예</span><span class="sxs-lookup"><span data-stu-id="ac88d-176">Examples</span></span>

<span data-ttu-id="ac88d-177">다음 예제에서는 클래스와 해당 멤버의 ID 문자열이 생성되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac88d-177">The following examples show how the ID strings for a class and its members are generated:</span></span>

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a><span data-ttu-id="ac88d-178">참조</span><span class="sxs-lookup"><span data-stu-id="ac88d-178">See also</span></span>

- [<span data-ttu-id="ac88d-179">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ac88d-179">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ac88d-180">-doc(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="ac88d-180">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="ac88d-181">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="ac88d-181">XML documentation comments</span></span>](./index.md)
