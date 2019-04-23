---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164686"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="c260a-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="c260a-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="c260a-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c260a-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="c260a-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="c260a-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="c260a-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c260a-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c260a-106">Tables</span><span class="sxs-lookup"><span data-stu-id="c260a-106">Tables</span></span>  
  
-   <span data-ttu-id="c260a-107">Columns</span><span class="sxs-lookup"><span data-stu-id="c260a-107">Columns</span></span>  
  
-   <span data-ttu-id="c260a-108">절차</span><span class="sxs-lookup"><span data-stu-id="c260a-108">Procedures</span></span>  
  
-   <span data-ttu-id="c260a-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c260a-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c260a-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="c260a-110">Catalog</span></span>  
  
-   <span data-ttu-id="c260a-111">인덱스</span><span class="sxs-lookup"><span data-stu-id="c260a-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="c260a-112">Tables</span><span class="sxs-lookup"><span data-stu-id="c260a-112">Tables</span></span>  
  
|<span data-ttu-id="c260a-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-113">ColumnName</span></span>|<span data-ttu-id="c260a-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-115">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-116">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-116">String</span></span>|  
|<span data-ttu-id="c260a-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-118">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-118">String</span></span>|  
|<span data-ttu-id="c260a-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-119">TABLE_NAME</span></span>|<span data-ttu-id="c260a-120">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-120">String</span></span>|  
|<span data-ttu-id="c260a-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-121">TABLE_TYPE</span></span>|<span data-ttu-id="c260a-122">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-122">String</span></span>|  
|<span data-ttu-id="c260a-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-123">TABLE_GUID</span></span>|<span data-ttu-id="c260a-124">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-124">Guid</span></span>|  
|<span data-ttu-id="c260a-125">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-125">DESCRIPTION</span></span>|<span data-ttu-id="c260a-126">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-126">String</span></span>|  
|<span data-ttu-id="c260a-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-127">TABLE_PROPID</span></span>|<span data-ttu-id="c260a-128">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-128">Int64</span></span>|  
|<span data-ttu-id="c260a-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-129">DATE_CREATED</span></span>|<span data-ttu-id="c260a-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-130">DateTime</span></span>|  
|<span data-ttu-id="c260a-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-131">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c260a-133">Columns</span><span class="sxs-lookup"><span data-stu-id="c260a-133">Columns</span></span>  
  
|<span data-ttu-id="c260a-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-134">ColumnName</span></span>|<span data-ttu-id="c260a-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-136">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-137">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-137">String</span></span>|  
|<span data-ttu-id="c260a-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-139">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-139">String</span></span>|  
|<span data-ttu-id="c260a-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-140">TABLE_NAME</span></span>|<span data-ttu-id="c260a-141">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-141">String</span></span>|  
|<span data-ttu-id="c260a-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-142">COLUMN_NAME</span></span>|<span data-ttu-id="c260a-143">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-143">String</span></span>|  
|<span data-ttu-id="c260a-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-144">COLUMN_GUID</span></span>|<span data-ttu-id="c260a-145">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-145">Guid</span></span>|  
|<span data-ttu-id="c260a-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-146">COLUMN_PROPID</span></span>|<span data-ttu-id="c260a-147">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-147">Int64</span></span>|  
|<span data-ttu-id="c260a-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-149">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-149">Int64</span></span>|  
|<span data-ttu-id="c260a-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="c260a-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-151">Boolean</span></span>|  
|<span data-ttu-id="c260a-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="c260a-153">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-153">String</span></span>|  
|<span data-ttu-id="c260a-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c260a-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="c260a-155">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-155">Int64</span></span>|  
|<span data-ttu-id="c260a-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-156">IS_NULLABLE</span></span>|<span data-ttu-id="c260a-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-157">Boolean</span></span>|  
|<span data-ttu-id="c260a-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-158">DATA_TYPE</span></span>|<span data-ttu-id="c260a-159">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-159">Int32</span></span>|  
|<span data-ttu-id="c260a-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-160">TYPE_GUID</span></span>|<span data-ttu-id="c260a-161">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-161">Guid</span></span>|  
|<span data-ttu-id="c260a-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c260a-163">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-163">Int64</span></span>|  
|<span data-ttu-id="c260a-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c260a-165">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-165">Int64</span></span>|  
|<span data-ttu-id="c260a-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c260a-167">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-167">Int32</span></span>|  
|<span data-ttu-id="c260a-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c260a-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="c260a-169">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-169">Int16</span></span>|  
|<span data-ttu-id="c260a-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="c260a-171">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-171">Int64</span></span>|  
|<span data-ttu-id="c260a-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="c260a-173">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-173">String</span></span>|  
|<span data-ttu-id="c260a-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="c260a-175">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-175">String</span></span>|  
|<span data-ttu-id="c260a-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="c260a-177">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-177">String</span></span>|  
|<span data-ttu-id="c260a-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="c260a-179">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-179">String</span></span>|  
|<span data-ttu-id="c260a-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="c260a-181">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-181">String</span></span>|  
|<span data-ttu-id="c260a-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-182">COLLATION_NAME</span></span>|<span data-ttu-id="c260a-183">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-183">String</span></span>|  
|<span data-ttu-id="c260a-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="c260a-185">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-185">String</span></span>|  
|<span data-ttu-id="c260a-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="c260a-187">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-187">String</span></span>|  
|<span data-ttu-id="c260a-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-188">DOMAIN_NAME</span></span>|<span data-ttu-id="c260a-189">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-189">String</span></span>|  
|<span data-ttu-id="c260a-190">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-190">DESCRIPTION</span></span>|<span data-ttu-id="c260a-191">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-191">String</span></span>|  
|<span data-ttu-id="c260a-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="c260a-192">COLUMN_LCID</span></span>|<span data-ttu-id="c260a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-193">Int32</span></span>|  
|<span data-ttu-id="c260a-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="c260a-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="c260a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-195">Int32</span></span>|  
|<span data-ttu-id="c260a-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="c260a-196">COLUMN_SORTID</span></span>|<span data-ttu-id="c260a-197">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-197">Int32</span></span>|  
|<span data-ttu-id="c260a-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="c260a-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="c260a-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="c260a-199">Byte[]</span></span>|  
|<span data-ttu-id="c260a-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="c260a-200">IS_COMPUTED</span></span>|<span data-ttu-id="c260a-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c260a-202">절차</span><span class="sxs-lookup"><span data-stu-id="c260a-202">Procedures</span></span>  
  
|<span data-ttu-id="c260a-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-203">ColumnName</span></span>|<span data-ttu-id="c260a-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c260a-206">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-206">String</span></span>|  
|<span data-ttu-id="c260a-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c260a-208">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-208">String</span></span>|  
|<span data-ttu-id="c260a-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="c260a-210">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-210">String</span></span>|  
|<span data-ttu-id="c260a-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c260a-212">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-212">Int16</span></span>|  
|<span data-ttu-id="c260a-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c260a-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="c260a-214">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-214">String</span></span>|  
|<span data-ttu-id="c260a-215">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-215">DESCRIPTION</span></span>|<span data-ttu-id="c260a-216">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-216">String</span></span>|  
|<span data-ttu-id="c260a-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-217">DATE_CREATED</span></span>|<span data-ttu-id="c260a-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-218">DateTime</span></span>|  
|<span data-ttu-id="c260a-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-219">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="c260a-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c260a-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="c260a-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-222">ColumnName</span></span>|<span data-ttu-id="c260a-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c260a-225">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-225">String</span></span>|  
|<span data-ttu-id="c260a-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c260a-227">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-227">String</span></span>|  
|<span data-ttu-id="c260a-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="c260a-229">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-229">String</span></span>|  
|<span data-ttu-id="c260a-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-230">PARAMETER_NAME</span></span>|<span data-ttu-id="c260a-231">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-231">String</span></span>|  
|<span data-ttu-id="c260a-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-233">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-233">Int32</span></span>|  
|<span data-ttu-id="c260a-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="c260a-235">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-235">Int32</span></span>|  
|<span data-ttu-id="c260a-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="c260a-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-237">Boolean</span></span>|  
|<span data-ttu-id="c260a-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="c260a-239">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-239">String</span></span>|  
|<span data-ttu-id="c260a-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-240">IS_NULLABLE</span></span>|<span data-ttu-id="c260a-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-241">Boolean</span></span>|  
|<span data-ttu-id="c260a-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-242">DATA_TYPE</span></span>|<span data-ttu-id="c260a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-243">Int32</span></span>|  
|<span data-ttu-id="c260a-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c260a-245">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-245">Int64</span></span>|  
|<span data-ttu-id="c260a-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c260a-247">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-247">Int64</span></span>|  
|<span data-ttu-id="c260a-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c260a-249">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-249">Int32</span></span>|  
|<span data-ttu-id="c260a-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c260a-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="c260a-251">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-251">Int16</span></span>|  
|<span data-ttu-id="c260a-252">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-252">DESCRIPTION</span></span>|<span data-ttu-id="c260a-253">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-253">String</span></span>|  
|<span data-ttu-id="c260a-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-254">TYPE_NAME</span></span>|<span data-ttu-id="c260a-255">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-255">String</span></span>|  
|<span data-ttu-id="c260a-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="c260a-257">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="c260a-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="c260a-258">Catalog</span></span>  
  
|<span data-ttu-id="c260a-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-259">ColumnName</span></span>|<span data-ttu-id="c260a-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-261">CATALOG_NAME</span></span>|<span data-ttu-id="c260a-262">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-262">String</span></span>|  
|<span data-ttu-id="c260a-263">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-263">DESCRIPTION</span></span>|<span data-ttu-id="c260a-264">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c260a-265">인덱스</span><span class="sxs-lookup"><span data-stu-id="c260a-265">Indexes</span></span>  
  
|<span data-ttu-id="c260a-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-266">ColumnName</span></span>|<span data-ttu-id="c260a-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-268">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-269">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-269">String</span></span>|  
|<span data-ttu-id="c260a-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-271">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-271">String</span></span>|  
|<span data-ttu-id="c260a-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-272">TABLE_NAME</span></span>|<span data-ttu-id="c260a-273">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-273">String</span></span>|  
|<span data-ttu-id="c260a-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-274">INDEX_CATALOG</span></span>|<span data-ttu-id="c260a-275">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-275">String</span></span>|  
|<span data-ttu-id="c260a-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="c260a-277">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-277">String</span></span>|  
|<span data-ttu-id="c260a-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-278">INDEX_NAME</span></span>|<span data-ttu-id="c260a-279">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-279">String</span></span>|  
|<span data-ttu-id="c260a-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="c260a-280">PRIMARY_KEY</span></span>|<span data-ttu-id="c260a-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-281">Boolean</span></span>|  
|<span data-ttu-id="c260a-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c260a-282">UNIQUE</span></span>|<span data-ttu-id="c260a-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-283">Boolean</span></span>|  
|<span data-ttu-id="c260a-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="c260a-284">CLUSTERED</span></span>|<span data-ttu-id="c260a-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-285">Boolean</span></span>|  
|<span data-ttu-id="c260a-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-286">TYPE</span></span>|<span data-ttu-id="c260a-287">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-287">Int32</span></span>|  
|<span data-ttu-id="c260a-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="c260a-288">FILL_FACTOR</span></span>|<span data-ttu-id="c260a-289">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-289">Int32</span></span>|  
|<span data-ttu-id="c260a-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="c260a-290">INITIAL_SIZE</span></span>|<span data-ttu-id="c260a-291">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-291">Int32</span></span>|  
|<span data-ttu-id="c260a-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="c260a-292">NULLS</span></span>|<span data-ttu-id="c260a-293">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-293">Int32</span></span>|  
|<span data-ttu-id="c260a-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="c260a-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="c260a-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-295">Boolean</span></span>|  
|<span data-ttu-id="c260a-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="c260a-296">AUTO_UPDATE</span></span>|<span data-ttu-id="c260a-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-297">Boolean</span></span>|  
|<span data-ttu-id="c260a-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="c260a-298">NULL_COLLATION</span></span>|<span data-ttu-id="c260a-299">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-299">Int32</span></span>|  
|<span data-ttu-id="c260a-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-301">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-301">Int64</span></span>|  
|<span data-ttu-id="c260a-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-302">COLUMN_NAME</span></span>|<span data-ttu-id="c260a-303">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-303">String</span></span>|  
|<span data-ttu-id="c260a-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-304">COLUMN_GUID</span></span>|<span data-ttu-id="c260a-305">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-305">Guid</span></span>|  
|<span data-ttu-id="c260a-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-306">COLUMN_PROPID</span></span>|<span data-ttu-id="c260a-307">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-307">Int64</span></span>|  
|<span data-ttu-id="c260a-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c260a-308">COLLATION</span></span>|<span data-ttu-id="c260a-309">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-309">Int16</span></span>|  
|<span data-ttu-id="c260a-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="c260a-310">CARDINALITY</span></span>|<span data-ttu-id="c260a-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="c260a-311">Decimal</span></span>|  
|<span data-ttu-id="c260a-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="c260a-312">PAGES</span></span>|<span data-ttu-id="c260a-313">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-313">Int32</span></span>|  
|<span data-ttu-id="c260a-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c260a-314">FILTER_CONDITION</span></span>|<span data-ttu-id="c260a-315">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-315">String</span></span>|  
|<span data-ttu-id="c260a-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="c260a-316">INTEGRATED</span></span>|<span data-ttu-id="c260a-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="c260a-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="c260a-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="c260a-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="c260a-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c260a-320">Tables</span><span class="sxs-lookup"><span data-stu-id="c260a-320">Tables</span></span>  
  
-   <span data-ttu-id="c260a-321">Columns</span><span class="sxs-lookup"><span data-stu-id="c260a-321">Columns</span></span>  
  
-   <span data-ttu-id="c260a-322">절차</span><span class="sxs-lookup"><span data-stu-id="c260a-322">Procedures</span></span>  
  
-   <span data-ttu-id="c260a-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c260a-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="c260a-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c260a-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c260a-325">보기</span><span class="sxs-lookup"><span data-stu-id="c260a-325">Views</span></span>  
  
-   <span data-ttu-id="c260a-326">인덱스</span><span class="sxs-lookup"><span data-stu-id="c260a-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="c260a-327">Tables</span><span class="sxs-lookup"><span data-stu-id="c260a-327">Tables</span></span>  
  
|<span data-ttu-id="c260a-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-328">ColumnName</span></span>|<span data-ttu-id="c260a-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-330">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-331">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-331">String</span></span>|  
|<span data-ttu-id="c260a-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-333">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-333">String</span></span>|  
|<span data-ttu-id="c260a-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-334">TABLE_NAME</span></span>|<span data-ttu-id="c260a-335">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-335">String</span></span>|  
|<span data-ttu-id="c260a-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-336">TABLE_TYPE</span></span>|<span data-ttu-id="c260a-337">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-337">String</span></span>|  
|<span data-ttu-id="c260a-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-338">TABLE_GUID</span></span>|<span data-ttu-id="c260a-339">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-339">Guid</span></span>|  
|<span data-ttu-id="c260a-340">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-340">DESCRIPTION</span></span>|<span data-ttu-id="c260a-341">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-341">String</span></span>|  
|<span data-ttu-id="c260a-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-342">TABLE_PROPID</span></span>|<span data-ttu-id="c260a-343">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-343">Int64</span></span>|  
|<span data-ttu-id="c260a-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-344">DATE_CREATED</span></span>|<span data-ttu-id="c260a-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-345">DateTime</span></span>|  
|<span data-ttu-id="c260a-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-346">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c260a-348">Columns</span><span class="sxs-lookup"><span data-stu-id="c260a-348">Columns</span></span>  
  
|<span data-ttu-id="c260a-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-349">ColumnName</span></span>|<span data-ttu-id="c260a-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-351">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-352">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-352">String</span></span>|  
|<span data-ttu-id="c260a-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-354">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-354">String</span></span>|  
|<span data-ttu-id="c260a-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-355">TABLE_NAME</span></span>|<span data-ttu-id="c260a-356">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-356">String</span></span>|  
|<span data-ttu-id="c260a-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-357">COLUMN_NAME</span></span>|<span data-ttu-id="c260a-358">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-358">String</span></span>|  
|<span data-ttu-id="c260a-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-359">COLUMN_GUID</span></span>|<span data-ttu-id="c260a-360">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-360">Guid</span></span>|  
|<span data-ttu-id="c260a-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-361">COLUMN_PROPID</span></span>|<span data-ttu-id="c260a-362">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-362">Int64</span></span>|  
|<span data-ttu-id="c260a-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-364">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-364">Int64</span></span>|  
|<span data-ttu-id="c260a-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="c260a-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-366">Boolean</span></span>|  
|<span data-ttu-id="c260a-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="c260a-368">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-368">String</span></span>|  
|<span data-ttu-id="c260a-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c260a-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="c260a-370">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-370">Int64</span></span>|  
|<span data-ttu-id="c260a-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-371">IS_NULLABLE</span></span>|<span data-ttu-id="c260a-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-372">Boolean</span></span>|  
|<span data-ttu-id="c260a-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-373">DATA_TYPE</span></span>|<span data-ttu-id="c260a-374">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-374">Int32</span></span>|  
|<span data-ttu-id="c260a-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-375">TYPE_GUID</span></span>|<span data-ttu-id="c260a-376">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-376">Guid</span></span>|  
|<span data-ttu-id="c260a-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c260a-378">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-378">Int64</span></span>|  
|<span data-ttu-id="c260a-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c260a-380">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-380">Int64</span></span>|  
|<span data-ttu-id="c260a-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c260a-382">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-382">Int32</span></span>|  
|<span data-ttu-id="c260a-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c260a-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="c260a-384">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-384">Int16</span></span>|  
|<span data-ttu-id="c260a-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="c260a-386">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-386">Int64</span></span>|  
|<span data-ttu-id="c260a-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="c260a-388">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-388">String</span></span>|  
|<span data-ttu-id="c260a-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="c260a-390">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-390">String</span></span>|  
|<span data-ttu-id="c260a-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="c260a-392">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-392">String</span></span>|  
|<span data-ttu-id="c260a-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="c260a-394">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-394">String</span></span>|  
|<span data-ttu-id="c260a-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="c260a-396">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-396">String</span></span>|  
|<span data-ttu-id="c260a-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-397">COLLATION_NAME</span></span>|<span data-ttu-id="c260a-398">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-398">String</span></span>|  
|<span data-ttu-id="c260a-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="c260a-400">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-400">String</span></span>|  
|<span data-ttu-id="c260a-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="c260a-402">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-402">String</span></span>|  
|<span data-ttu-id="c260a-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-403">DOMAIN_NAME</span></span>|<span data-ttu-id="c260a-404">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-404">String</span></span>|  
|<span data-ttu-id="c260a-405">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-405">DESCRIPTION</span></span>|<span data-ttu-id="c260a-406">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c260a-407">절차</span><span class="sxs-lookup"><span data-stu-id="c260a-407">Procedures</span></span>  
  
|<span data-ttu-id="c260a-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-408">ColumnName</span></span>|<span data-ttu-id="c260a-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c260a-411">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-411">String</span></span>|  
|<span data-ttu-id="c260a-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c260a-413">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-413">String</span></span>|  
|<span data-ttu-id="c260a-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="c260a-415">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-415">String</span></span>|  
|<span data-ttu-id="c260a-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c260a-417">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-417">Int16</span></span>|  
|<span data-ttu-id="c260a-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c260a-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="c260a-419">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-419">String</span></span>|  
|<span data-ttu-id="c260a-420">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-420">DESCRIPTION</span></span>|<span data-ttu-id="c260a-421">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-421">String</span></span>|  
|<span data-ttu-id="c260a-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-422">DATE_CREATED</span></span>|<span data-ttu-id="c260a-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-423">DateTime</span></span>|  
|<span data-ttu-id="c260a-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-424">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c260a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c260a-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c260a-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-427">ColumnName</span></span>|<span data-ttu-id="c260a-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c260a-430">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-430">String</span></span>|  
|<span data-ttu-id="c260a-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c260a-432">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-432">String</span></span>|  
|<span data-ttu-id="c260a-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="c260a-434">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-434">String</span></span>|  
|<span data-ttu-id="c260a-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-435">COLUMN_NAME</span></span>|<span data-ttu-id="c260a-436">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-436">String</span></span>|  
|<span data-ttu-id="c260a-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-437">COLUMN_GUID</span></span>|<span data-ttu-id="c260a-438">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-438">Guid</span></span>|  
|<span data-ttu-id="c260a-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-439">COLUMN_PROPID</span></span>|<span data-ttu-id="c260a-440">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-440">Int64</span></span>|  
|<span data-ttu-id="c260a-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="c260a-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="c260a-442">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-442">Int64</span></span>|  
|<span data-ttu-id="c260a-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-444">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-444">Int64</span></span>|  
|<span data-ttu-id="c260a-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-445">IS_NULLABLE</span></span>|<span data-ttu-id="c260a-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-446">Boolean</span></span>|  
|<span data-ttu-id="c260a-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-447">DATA_TYPE</span></span>|<span data-ttu-id="c260a-448">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-448">Int32</span></span>|  
|<span data-ttu-id="c260a-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-449">TYPE_GUID</span></span>|<span data-ttu-id="c260a-450">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-450">Guid</span></span>|  
|<span data-ttu-id="c260a-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c260a-452">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-452">Int64</span></span>|  
|<span data-ttu-id="c260a-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c260a-454">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-454">Int64</span></span>|  
|<span data-ttu-id="c260a-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c260a-456">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-456">Int32</span></span>|  
|<span data-ttu-id="c260a-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c260a-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="c260a-458">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-458">Int16</span></span>|  
|<span data-ttu-id="c260a-459">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-459">DESCRIPTION</span></span>|<span data-ttu-id="c260a-460">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-460">String</span></span>|  
|<span data-ttu-id="c260a-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c260a-461">OVERLOAD</span></span>|<span data-ttu-id="c260a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="c260a-463">보기</span><span class="sxs-lookup"><span data-stu-id="c260a-463">Views</span></span>  
  
|<span data-ttu-id="c260a-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-464">ColumnName</span></span>|<span data-ttu-id="c260a-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-466">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-467">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-467">String</span></span>|  
|<span data-ttu-id="c260a-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-469">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-469">String</span></span>|  
|<span data-ttu-id="c260a-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-470">TABLE_NAME</span></span>|<span data-ttu-id="c260a-471">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-471">String</span></span>|  
|<span data-ttu-id="c260a-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c260a-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="c260a-473">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-473">String</span></span>|  
|<span data-ttu-id="c260a-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="c260a-474">CHECK_OPTION</span></span>|<span data-ttu-id="c260a-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-475">Boolean</span></span>|  
|<span data-ttu-id="c260a-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-476">IS_UPDATABLE</span></span>|<span data-ttu-id="c260a-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-477">Boolean</span></span>|  
|<span data-ttu-id="c260a-478">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-478">DESCRIPTION</span></span>|<span data-ttu-id="c260a-479">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-479">String</span></span>|  
|<span data-ttu-id="c260a-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-480">DATE_CREATED</span></span>|<span data-ttu-id="c260a-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-481">DateTime</span></span>|  
|<span data-ttu-id="c260a-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-482">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c260a-484">인덱스</span><span class="sxs-lookup"><span data-stu-id="c260a-484">Indexes</span></span>  
  
|<span data-ttu-id="c260a-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-485">ColumnName</span></span>|<span data-ttu-id="c260a-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-487">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-488">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-488">String</span></span>|  
|<span data-ttu-id="c260a-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-490">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-490">String</span></span>|  
|<span data-ttu-id="c260a-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-491">TABLE_NAME</span></span>|<span data-ttu-id="c260a-492">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-492">String</span></span>|  
|<span data-ttu-id="c260a-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-493">INDEX_CATALOG</span></span>|<span data-ttu-id="c260a-494">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-494">String</span></span>|  
|<span data-ttu-id="c260a-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="c260a-496">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-496">String</span></span>|  
|<span data-ttu-id="c260a-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-497">INDEX_NAME</span></span>|<span data-ttu-id="c260a-498">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-498">String</span></span>|  
|<span data-ttu-id="c260a-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="c260a-499">PRIMARY_KEY</span></span>|<span data-ttu-id="c260a-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-500">Boolean</span></span>|  
|<span data-ttu-id="c260a-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c260a-501">UNIQUE</span></span>|<span data-ttu-id="c260a-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-502">Boolean</span></span>|  
|<span data-ttu-id="c260a-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="c260a-503">CLUSTERED</span></span>|<span data-ttu-id="c260a-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-504">Boolean</span></span>|  
|<span data-ttu-id="c260a-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-505">TYPE</span></span>|<span data-ttu-id="c260a-506">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-506">Int32</span></span>|  
|<span data-ttu-id="c260a-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="c260a-507">FILL_FACTOR</span></span>|<span data-ttu-id="c260a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-508">Int32</span></span>|  
|<span data-ttu-id="c260a-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="c260a-509">INITIAL_SIZE</span></span>|<span data-ttu-id="c260a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-510">Int32</span></span>|  
|<span data-ttu-id="c260a-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="c260a-511">NULLS</span></span>|<span data-ttu-id="c260a-512">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-512">Int32</span></span>|  
|<span data-ttu-id="c260a-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="c260a-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="c260a-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-514">Boolean</span></span>|  
|<span data-ttu-id="c260a-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="c260a-515">AUTO_UPDATE</span></span>|<span data-ttu-id="c260a-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-516">Boolean</span></span>|  
|<span data-ttu-id="c260a-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="c260a-517">NULL_COLLATION</span></span>|<span data-ttu-id="c260a-518">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-518">Int32</span></span>|  
|<span data-ttu-id="c260a-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-520">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-520">Int64</span></span>|  
|<span data-ttu-id="c260a-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-521">COLUMN_NAME</span></span>|<span data-ttu-id="c260a-522">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-522">String</span></span>|  
|<span data-ttu-id="c260a-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-523">COLUMN_GUID</span></span>|<span data-ttu-id="c260a-524">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-524">Guid</span></span>|  
|<span data-ttu-id="c260a-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-525">COLUMN_PROPID</span></span>|<span data-ttu-id="c260a-526">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-526">Int64</span></span>|  
|<span data-ttu-id="c260a-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c260a-527">COLLATION</span></span>|<span data-ttu-id="c260a-528">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-528">Int16</span></span>|  
|<span data-ttu-id="c260a-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="c260a-529">CARDINALITY</span></span>|<span data-ttu-id="c260a-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="c260a-530">Decimal</span></span>|  
|<span data-ttu-id="c260a-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="c260a-531">PAGES</span></span>|<span data-ttu-id="c260a-532">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-532">Int32</span></span>|  
|<span data-ttu-id="c260a-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c260a-533">FILTER_CONDITION</span></span>|<span data-ttu-id="c260a-534">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-534">String</span></span>|  
|<span data-ttu-id="c260a-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="c260a-535">INTEGRATED</span></span>|<span data-ttu-id="c260a-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="c260a-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="c260a-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="c260a-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="c260a-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c260a-539">Tables</span><span class="sxs-lookup"><span data-stu-id="c260a-539">Tables</span></span>  
  
-   <span data-ttu-id="c260a-540">Columns</span><span class="sxs-lookup"><span data-stu-id="c260a-540">Columns</span></span>  
  
-   <span data-ttu-id="c260a-541">절차</span><span class="sxs-lookup"><span data-stu-id="c260a-541">Procedures</span></span>  
  
-   <span data-ttu-id="c260a-542">보기</span><span class="sxs-lookup"><span data-stu-id="c260a-542">Views</span></span>  
  
-   <span data-ttu-id="c260a-543">인덱스</span><span class="sxs-lookup"><span data-stu-id="c260a-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="c260a-544">Tables</span><span class="sxs-lookup"><span data-stu-id="c260a-544">Tables</span></span>  
  
|<span data-ttu-id="c260a-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-545">ColumnName</span></span>|<span data-ttu-id="c260a-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-547">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-548">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-548">String</span></span>|  
|<span data-ttu-id="c260a-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-550">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-550">String</span></span>|  
|<span data-ttu-id="c260a-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-551">TABLE_NAME</span></span>|<span data-ttu-id="c260a-552">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-552">String</span></span>|  
|<span data-ttu-id="c260a-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-553">TABLE_TYPE</span></span>|<span data-ttu-id="c260a-554">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-554">String</span></span>|  
|<span data-ttu-id="c260a-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-555">TABLE_GUID</span></span>|<span data-ttu-id="c260a-556">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-556">Guid</span></span>|  
|<span data-ttu-id="c260a-557">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-557">DESCRIPTION</span></span>|<span data-ttu-id="c260a-558">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-558">String</span></span>|  
|<span data-ttu-id="c260a-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-559">TABLE_PROPID</span></span>|<span data-ttu-id="c260a-560">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-560">Int64</span></span>|  
|<span data-ttu-id="c260a-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-561">DATE_CREATED</span></span>|<span data-ttu-id="c260a-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-562">DateTime</span></span>|  
|<span data-ttu-id="c260a-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-563">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c260a-565">Columns</span><span class="sxs-lookup"><span data-stu-id="c260a-565">Columns</span></span>  
  
|<span data-ttu-id="c260a-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-566">ColumnName</span></span>|<span data-ttu-id="c260a-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-568">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-569">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-569">String</span></span>|  
|<span data-ttu-id="c260a-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-571">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-571">String</span></span>|  
|<span data-ttu-id="c260a-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-572">TABLE_NAME</span></span>|<span data-ttu-id="c260a-573">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-573">String</span></span>|  
|<span data-ttu-id="c260a-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-574">COLUMN_NAME</span></span>|<span data-ttu-id="c260a-575">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-575">String</span></span>|  
|<span data-ttu-id="c260a-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-576">COLUMN_GUID</span></span>|<span data-ttu-id="c260a-577">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-577">Guid</span></span>|  
|<span data-ttu-id="c260a-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-578">COLUMN_PROPID</span></span>|<span data-ttu-id="c260a-579">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-579">Int64</span></span>|  
|<span data-ttu-id="c260a-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-581">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-581">Int64</span></span>|  
|<span data-ttu-id="c260a-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="c260a-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-583">Boolean</span></span>|  
|<span data-ttu-id="c260a-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c260a-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="c260a-585">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-585">String</span></span>|  
|<span data-ttu-id="c260a-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c260a-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="c260a-587">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-587">Int64</span></span>|  
|<span data-ttu-id="c260a-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-588">IS_NULLABLE</span></span>|<span data-ttu-id="c260a-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-589">Boolean</span></span>|  
|<span data-ttu-id="c260a-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-590">DATA_TYPE</span></span>|<span data-ttu-id="c260a-591">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-591">Int32</span></span>|  
|<span data-ttu-id="c260a-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-592">TYPE_GUID</span></span>|<span data-ttu-id="c260a-593">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-593">Guid</span></span>|  
|<span data-ttu-id="c260a-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c260a-595">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-595">Int64</span></span>|  
|<span data-ttu-id="c260a-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c260a-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c260a-597">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-597">Int64</span></span>|  
|<span data-ttu-id="c260a-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c260a-599">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-599">Int32</span></span>|  
|<span data-ttu-id="c260a-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c260a-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="c260a-601">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-601">Int16</span></span>|  
|<span data-ttu-id="c260a-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c260a-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="c260a-603">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-603">Int64</span></span>|  
|<span data-ttu-id="c260a-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="c260a-605">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-605">String</span></span>|  
|<span data-ttu-id="c260a-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="c260a-607">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-607">String</span></span>|  
|<span data-ttu-id="c260a-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="c260a-609">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-609">String</span></span>|  
|<span data-ttu-id="c260a-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="c260a-611">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-611">String</span></span>|  
|<span data-ttu-id="c260a-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="c260a-613">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-613">String</span></span>|  
|<span data-ttu-id="c260a-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-614">COLLATION_NAME</span></span>|<span data-ttu-id="c260a-615">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-615">String</span></span>|  
|<span data-ttu-id="c260a-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="c260a-617">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-617">String</span></span>|  
|<span data-ttu-id="c260a-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="c260a-619">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-619">String</span></span>|  
|<span data-ttu-id="c260a-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-620">DOMAIN_NAME</span></span>|<span data-ttu-id="c260a-621">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-621">String</span></span>|  
|<span data-ttu-id="c260a-622">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-622">DESCRIPTION</span></span>|<span data-ttu-id="c260a-623">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c260a-624">절차</span><span class="sxs-lookup"><span data-stu-id="c260a-624">Procedures</span></span>  
  
|<span data-ttu-id="c260a-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-625">ColumnName</span></span>|<span data-ttu-id="c260a-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c260a-628">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-628">String</span></span>|  
|<span data-ttu-id="c260a-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c260a-630">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-630">String</span></span>|  
|<span data-ttu-id="c260a-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="c260a-632">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-632">String</span></span>|  
|<span data-ttu-id="c260a-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c260a-634">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-634">Int16</span></span>|  
|<span data-ttu-id="c260a-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c260a-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="c260a-636">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-636">String</span></span>|  
|<span data-ttu-id="c260a-637">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-637">DESCRIPTION</span></span>|<span data-ttu-id="c260a-638">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-638">String</span></span>|  
|<span data-ttu-id="c260a-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-639">DATE_CREATED</span></span>|<span data-ttu-id="c260a-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-640">DateTime</span></span>|  
|<span data-ttu-id="c260a-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-641">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="c260a-643">보기</span><span class="sxs-lookup"><span data-stu-id="c260a-643">Views</span></span>  
  
|<span data-ttu-id="c260a-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-644">ColumnName</span></span>|<span data-ttu-id="c260a-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-646">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-647">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-647">String</span></span>|  
|<span data-ttu-id="c260a-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-649">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-649">String</span></span>|  
|<span data-ttu-id="c260a-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-650">TABLE_NAME</span></span>|<span data-ttu-id="c260a-651">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-651">String</span></span>|  
|<span data-ttu-id="c260a-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c260a-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="c260a-653">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-653">String</span></span>|  
|<span data-ttu-id="c260a-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="c260a-654">CHECK_OPTION</span></span>|<span data-ttu-id="c260a-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-655">Boolean</span></span>|  
|<span data-ttu-id="c260a-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-656">IS_UPDATABLE</span></span>|<span data-ttu-id="c260a-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-657">Boolean</span></span>|  
|<span data-ttu-id="c260a-658">설명</span><span class="sxs-lookup"><span data-stu-id="c260a-658">DESCRIPTION</span></span>|<span data-ttu-id="c260a-659">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-659">String</span></span>|  
|<span data-ttu-id="c260a-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c260a-660">DATE_CREATED</span></span>|<span data-ttu-id="c260a-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-661">DateTime</span></span>|  
|<span data-ttu-id="c260a-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c260a-662">DATE_MODIFIED</span></span>|<span data-ttu-id="c260a-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="c260a-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c260a-664">인덱스</span><span class="sxs-lookup"><span data-stu-id="c260a-664">Indexes</span></span>  
  
|<span data-ttu-id="c260a-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="c260a-665">ColumnName</span></span>|<span data-ttu-id="c260a-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c260a-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c260a-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-667">TABLE_CATALOG</span></span>|<span data-ttu-id="c260a-668">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-668">String</span></span>|  
|<span data-ttu-id="c260a-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="c260a-670">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-670">String</span></span>|  
|<span data-ttu-id="c260a-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-671">TABLE_NAME</span></span>|<span data-ttu-id="c260a-672">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-672">String</span></span>|  
|<span data-ttu-id="c260a-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c260a-673">INDEX_CATALOG</span></span>|<span data-ttu-id="c260a-674">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-674">String</span></span>|  
|<span data-ttu-id="c260a-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c260a-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="c260a-676">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-676">String</span></span>|  
|<span data-ttu-id="c260a-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-677">INDEX_NAME</span></span>|<span data-ttu-id="c260a-678">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-678">String</span></span>|  
|<span data-ttu-id="c260a-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="c260a-679">PRIMARY_KEY</span></span>|<span data-ttu-id="c260a-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-680">Boolean</span></span>|  
|<span data-ttu-id="c260a-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c260a-681">UNIQUE</span></span>|<span data-ttu-id="c260a-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-682">Boolean</span></span>|  
|<span data-ttu-id="c260a-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="c260a-683">CLUSTERED</span></span>|<span data-ttu-id="c260a-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-684">Boolean</span></span>|  
|<span data-ttu-id="c260a-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="c260a-685">TYPE</span></span>|<span data-ttu-id="c260a-686">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-686">Int32</span></span>|  
|<span data-ttu-id="c260a-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="c260a-687">FILL_FACTOR</span></span>|<span data-ttu-id="c260a-688">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-688">Int32</span></span>|  
|<span data-ttu-id="c260a-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="c260a-689">INITIAL_SIZE</span></span>|<span data-ttu-id="c260a-690">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-690">Int32</span></span>|  
|<span data-ttu-id="c260a-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="c260a-691">NULLS</span></span>|<span data-ttu-id="c260a-692">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-692">Int32</span></span>|  
|<span data-ttu-id="c260a-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="c260a-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="c260a-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-694">Boolean</span></span>|  
|<span data-ttu-id="c260a-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="c260a-695">AUTO_UPDATE</span></span>|<span data-ttu-id="c260a-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-696">Boolean</span></span>|  
|<span data-ttu-id="c260a-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="c260a-697">NULL_COLLATION</span></span>|<span data-ttu-id="c260a-698">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-698">Int32</span></span>|  
|<span data-ttu-id="c260a-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c260a-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="c260a-700">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-700">Int64</span></span>|  
|<span data-ttu-id="c260a-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c260a-701">COLUMN_NAME</span></span>|<span data-ttu-id="c260a-702">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-702">String</span></span>|  
|<span data-ttu-id="c260a-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c260a-703">COLUMN_GUID</span></span>|<span data-ttu-id="c260a-704">Guid</span><span class="sxs-lookup"><span data-stu-id="c260a-704">Guid</span></span>|  
|<span data-ttu-id="c260a-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c260a-705">COLUMN_PROPID</span></span>|<span data-ttu-id="c260a-706">Int64</span><span class="sxs-lookup"><span data-stu-id="c260a-706">Int64</span></span>|  
|<span data-ttu-id="c260a-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c260a-707">COLLATION</span></span>|<span data-ttu-id="c260a-708">Int16</span><span class="sxs-lookup"><span data-stu-id="c260a-708">Int16</span></span>|  
|<span data-ttu-id="c260a-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="c260a-709">CARDINALITY</span></span>|<span data-ttu-id="c260a-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="c260a-710">Decimal</span></span>|  
|<span data-ttu-id="c260a-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="c260a-711">PAGES</span></span>|<span data-ttu-id="c260a-712">Int32</span><span class="sxs-lookup"><span data-stu-id="c260a-712">Int32</span></span>|  
|<span data-ttu-id="c260a-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c260a-713">FILTER_CONDITION</span></span>|<span data-ttu-id="c260a-714">문자열</span><span class="sxs-lookup"><span data-stu-id="c260a-714">String</span></span>|  
|<span data-ttu-id="c260a-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="c260a-715">INTEGRATED</span></span>|<span data-ttu-id="c260a-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="c260a-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c260a-717">참고자료</span><span class="sxs-lookup"><span data-stu-id="c260a-717">See also</span></span>

- [<span data-ttu-id="c260a-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c260a-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
