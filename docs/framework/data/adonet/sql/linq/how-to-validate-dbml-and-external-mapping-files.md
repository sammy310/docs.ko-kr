---
description: '자세한 정보: 방법: DBML 및 외부 매핑 파일 유효성 검사'
title: '방법: DBML 및 외부 매핑 파일 유효성 검사'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 46e5c787bef8e152020fc97631ef8c1c4928fe74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785785"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="6a72a-103">방법: DBML 및 외부 매핑 파일 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="6a72a-103">How to: Validate DBML and External Mapping Files</span></span>

<span data-ttu-id="6a72a-104">수정한 외부 매핑 파일 및 .dbml 파일은 해당 스키마 정의에 대해 유효성이 검사되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-104">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="6a72a-105">이 항목에서는 Visual Studio 사용자에 게 유효성 검사 프로세스를 구현 하는 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-105">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="6a72a-106">.dbml 또는 XML 파일의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="6a72a-106">To validate a .dbml or XML file</span></span>

1. <span data-ttu-id="6a72a-107">Visual Studio **파일** 메뉴에서 **열기** 를 가리킨 다음 **파일** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-107">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>

2. <span data-ttu-id="6a72a-108">**파일 열기** 대화 상자에서 유효성 검사를 수행 하려는 .DBML 또는 XML 매핑 파일을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-108">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>

    <span data-ttu-id="6a72a-109">파일이 **XML 편집기** 에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-109">The file opens in the **XML Editor**.</span></span>

3. <span data-ttu-id="6a72a-110">창을 마우스 오른쪽 단추로 클릭 한 다음 **속성** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-110">Right-click the window, and then click **Properties**.</span></span>

4. <span data-ttu-id="6a72a-111">**속성** 창에서 **스키마** 속성에 대 한 줄임표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-111">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>

    <span data-ttu-id="6a72a-112">**XML 스키마** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-112">The **XML Schemas** dialog box opens.</span></span>

5. <span data-ttu-id="6a72a-113">원하는 목적에 맞는 적절한 스키마 정의를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-113">Note the appropriate schema definition for your purpose.</span></span>

    - <span data-ttu-id="6a72a-114">DbmlSchema.xsd는 .dbml 파일의 유효성 검사를 위한 스키마 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-114">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="6a72a-115">자세한 내용은 [LINQ to SQL에서 코드 생성](code-generation-in-linq-to-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a72a-115">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>

    - <span data-ttu-id="6a72a-116">LinqToSqlMapping.xsd는 외부 XML 매핑 파일의 유효성 검사를 위한 스키마 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-116">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="6a72a-117">자세한 내용은 [외부 매핑](external-mapping.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a72a-117">For more information, see [External Mapping](external-mapping.md).</span></span>

6. <span data-ttu-id="6a72a-118">원하는 스키마 정의 행의 **사용** 열에서 드롭다운 상자를 클릭 하 여 연 다음 **이 스키마 사용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-118">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>

    <span data-ttu-id="6a72a-119">이제 스키마 정의 파일이 DBML 또는 XML 매핑 파일과 연관됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-119">The schema definition file is now associated with your DBML or XML mapping file.</span></span>

    <span data-ttu-id="6a72a-120">다른 스키마 정의가 선택되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-120">Make sure no other schema definitions are selected.</span></span>

7. <span data-ttu-id="6a72a-121">**보기** 메뉴에서 **오류 목록** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-121">On the **View** menu, click **Error List**.</span></span>

    <span data-ttu-id="6a72a-122">오류, 경고 또는 메시지가 생성되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-122">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="6a72a-123">생성된 것이 없는 경우 스키마 정의에 대해 XML 파일이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-123">If not, the XML file is valid against the schema definition.</span></span>

## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="6a72a-124">스키마 정의 제공을 위한 대체 방법</span><span class="sxs-lookup"><span data-stu-id="6a72a-124">Alternate Method for Supplying Schema Definition</span></span>

<span data-ttu-id="6a72a-125">어떤 이유로 든 적절 한 .xsd 파일이 **XML 스키마** 대화 상자에 표시 되지 않으면 도움말 항목에서 .xsd 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-125">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="6a72a-126">다음 단계를 통해 Visual Studio XML 편집기에 필요한 유니코드 형식으로 다운로드 한 파일을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-126">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>

#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="6a72a-127">도움말 항목에서 스키마 정의 파일을 복사하려면</span><span class="sxs-lookup"><span data-stu-id="6a72a-127">To copy a schema definition file from a Help topic</span></span>

1. <span data-ttu-id="6a72a-128">이 항목의 앞부분에서 설명한 대로 스키마 정의가 포함된 도움말 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-128">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>

    - <span data-ttu-id="6a72a-129">.Dbml 파일은 [LINQ to SQL에서 코드 생성](code-generation-in-linq-to-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a72a-129">For .dbml files, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>

    - <span data-ttu-id="6a72a-130">외부 매핑 파일은 [외부 매핑](external-mapping.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a72a-130">For external mapping files, see [External Mapping](external-mapping.md).</span></span>

2. <span data-ttu-id="6a72a-131">코드 **복사** 를 클릭 하 여 코드 파일을 클립보드에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-131">Click **Copy Code** to copy the code file to the Clipboard.</span></span>

3. <span data-ttu-id="6a72a-132">메모장을 시작하여 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-132">Start Notepad to create a new file.</span></span>

4. <span data-ttu-id="6a72a-133">클립보드에서 메모장 파일로 코드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-133">Paste the code from the clipboard into Notepad file.</span></span>

5. <span data-ttu-id="6a72a-134">메모장 **파일** 메뉴에서 다른 **이름으로 저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-134">On the Notepad **File** menu, click **Save As**.</span></span>

6. <span data-ttu-id="6a72a-135">**인코딩** 상자에서 **유니코드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-135">In the **Encoding** box, select **Unicode**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6a72a-136">이렇게 하면 유니코드 16바이트 순서 마커(`FFFE`)가 텍스트 파일 앞에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-136">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>

7. <span data-ttu-id="6a72a-137">**파일 이름** 상자에서 확장명이 .xsd 인 파일 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a72a-137">In the **File name** box, create a file name with an .xsd extension.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a72a-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a72a-138">See also</span></span>

- [<span data-ttu-id="6a72a-139">참조</span><span class="sxs-lookup"><span data-stu-id="6a72a-139">Reference</span></span>](reference.md)
