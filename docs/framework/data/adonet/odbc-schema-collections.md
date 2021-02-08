---
description: '자세한 정보: ODBC 스키마 컬렉션'
title: ODBC 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ceac67e49914db7010e315a2dfcdb630bea1e29f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786201"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="33001-103">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="33001-103">ODBC Schema Collections</span></span>

<span data-ttu-id="33001-104">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33001-104">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="33001-105">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="33001-105">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="33001-106">Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33001-106">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="33001-107">테이블</span><span class="sxs-lookup"><span data-stu-id="33001-107">Tables</span></span>

- <span data-ttu-id="33001-108">인덱스</span><span class="sxs-lookup"><span data-stu-id="33001-108">Indexes</span></span>

- <span data-ttu-id="33001-109">열</span><span class="sxs-lookup"><span data-stu-id="33001-109">Columns</span></span>

- <span data-ttu-id="33001-110">프로시저</span><span class="sxs-lookup"><span data-stu-id="33001-110">Procedures</span></span>

- <span data-ttu-id="33001-111">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33001-111">ProcedureColumns</span></span>

- <span data-ttu-id="33001-112">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33001-112">ProcedureParameters</span></span>

- <span data-ttu-id="33001-113">보기</span><span class="sxs-lookup"><span data-stu-id="33001-113">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="33001-114">테이블 및 뷰</span><span class="sxs-lookup"><span data-stu-id="33001-114">Tables and Views</span></span>

|<span data-ttu-id="33001-115">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-115">ColumnName</span></span>|<span data-ttu-id="33001-116">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-116">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-117">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="33001-117">TABLE_CAT</span></span>|<span data-ttu-id="33001-118">String</span><span class="sxs-lookup"><span data-stu-id="33001-118">String</span></span>|
|<span data-ttu-id="33001-119">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="33001-119">TABLE_SCHEM</span></span>|<span data-ttu-id="33001-120">String</span><span class="sxs-lookup"><span data-stu-id="33001-120">String</span></span>|
|<span data-ttu-id="33001-121">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-121">TABLE_NAME</span></span>|<span data-ttu-id="33001-122">String</span><span class="sxs-lookup"><span data-stu-id="33001-122">String</span></span>|
|<span data-ttu-id="33001-123">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-123">TABLE_TYPE</span></span>|<span data-ttu-id="33001-124">String</span><span class="sxs-lookup"><span data-stu-id="33001-124">String</span></span>|
|<span data-ttu-id="33001-125">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-125">REMARKS</span></span>|<span data-ttu-id="33001-126">String</span><span class="sxs-lookup"><span data-stu-id="33001-126">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="33001-127">인덱스</span><span class="sxs-lookup"><span data-stu-id="33001-127">Indexes</span></span>

|<span data-ttu-id="33001-128">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-128">ColumnName</span></span>|<span data-ttu-id="33001-129">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-129">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-130">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="33001-130">TABLE_CAT</span></span>|<span data-ttu-id="33001-131">String</span><span class="sxs-lookup"><span data-stu-id="33001-131">String</span></span>|
|<span data-ttu-id="33001-132">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="33001-132">TABLE_SCHEM</span></span>|<span data-ttu-id="33001-133">String</span><span class="sxs-lookup"><span data-stu-id="33001-133">String</span></span>|
|<span data-ttu-id="33001-134">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-134">TABLE_NAME</span></span>|<span data-ttu-id="33001-135">String</span><span class="sxs-lookup"><span data-stu-id="33001-135">String</span></span>|
|<span data-ttu-id="33001-136">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="33001-136">NON_UNIQUE</span></span>|<span data-ttu-id="33001-137">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-137">Int16</span></span>|
|<span data-ttu-id="33001-138">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-138">INDEX_QUALIFIER</span></span>|<span data-ttu-id="33001-139">String</span><span class="sxs-lookup"><span data-stu-id="33001-139">String</span></span>|
|<span data-ttu-id="33001-140">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-140">INDEX_NAME</span></span>|<span data-ttu-id="33001-141">String</span><span class="sxs-lookup"><span data-stu-id="33001-141">String</span></span>|
|<span data-ttu-id="33001-142">TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-142">TYPE</span></span>|<span data-ttu-id="33001-143">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-143">Int16</span></span>|
|<span data-ttu-id="33001-144">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-144">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-145">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-145">Int16</span></span>|
|<span data-ttu-id="33001-146">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-146">COLUMN_NAME</span></span>|<span data-ttu-id="33001-147">String</span><span class="sxs-lookup"><span data-stu-id="33001-147">String</span></span>|
|<span data-ttu-id="33001-148">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="33001-148">ASC_OR_DESC</span></span>|<span data-ttu-id="33001-149">String</span><span class="sxs-lookup"><span data-stu-id="33001-149">String</span></span>|
|<span data-ttu-id="33001-150">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="33001-150">CARDINALITY</span></span>|<span data-ttu-id="33001-151">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-151">Int32</span></span>|
|<span data-ttu-id="33001-152">PAGES</span><span class="sxs-lookup"><span data-stu-id="33001-152">PAGES</span></span>|<span data-ttu-id="33001-153">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-153">Int32</span></span>|
|<span data-ttu-id="33001-154">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="33001-154">FILTER_CONDITION</span></span>|<span data-ttu-id="33001-155">String</span><span class="sxs-lookup"><span data-stu-id="33001-155">String</span></span>|
|<span data-ttu-id="33001-156">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33001-156">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="33001-157">String</span><span class="sxs-lookup"><span data-stu-id="33001-157">String</span></span>|
|<span data-ttu-id="33001-158">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-158">SS_DATA_TYPE</span></span>|<span data-ttu-id="33001-159">Byte</span><span class="sxs-lookup"><span data-stu-id="33001-159">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="33001-160">열</span><span class="sxs-lookup"><span data-stu-id="33001-160">Columns</span></span>

|<span data-ttu-id="33001-161">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-161">ColumnName</span></span>|<span data-ttu-id="33001-162">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-162">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-163">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="33001-163">TABLE_CAT</span></span>|<span data-ttu-id="33001-164">String</span><span class="sxs-lookup"><span data-stu-id="33001-164">String</span></span>|
|<span data-ttu-id="33001-165">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="33001-165">TABLE_SCHEM</span></span>|<span data-ttu-id="33001-166">String</span><span class="sxs-lookup"><span data-stu-id="33001-166">String</span></span>|
|<span data-ttu-id="33001-167">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-167">TABLE_NAME</span></span>|<span data-ttu-id="33001-168">String</span><span class="sxs-lookup"><span data-stu-id="33001-168">String</span></span>|
|<span data-ttu-id="33001-169">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-169">COLUMN_NAME</span></span>|<span data-ttu-id="33001-170">String</span><span class="sxs-lookup"><span data-stu-id="33001-170">String</span></span>|
|<span data-ttu-id="33001-171">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-171">DATA_TYPE</span></span>|<span data-ttu-id="33001-172">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-172">Int16</span></span>|
|<span data-ttu-id="33001-173">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-173">TYPE_NAME</span></span>|<span data-ttu-id="33001-174">String</span><span class="sxs-lookup"><span data-stu-id="33001-174">String</span></span>|
|<span data-ttu-id="33001-175">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="33001-175">COLUMN_SIZE</span></span>|<span data-ttu-id="33001-176">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-176">Int32</span></span>|
|<span data-ttu-id="33001-177">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-177">BUFFER_LENGTH</span></span>|<span data-ttu-id="33001-178">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-178">Int32</span></span>|
|<span data-ttu-id="33001-179">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="33001-179">DECIMAL_DIGITS</span></span>|<span data-ttu-id="33001-180">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-180">Int16</span></span>|
|<span data-ttu-id="33001-181">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-181">NUM_PREC_RADIX</span></span>|<span data-ttu-id="33001-182">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-182">Int16</span></span>|
|<span data-ttu-id="33001-183">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-183">NULLABLE</span></span>|<span data-ttu-id="33001-184">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-184">Int16</span></span>|
|<span data-ttu-id="33001-185">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-185">REMARKS</span></span>|<span data-ttu-id="33001-186">String</span><span class="sxs-lookup"><span data-stu-id="33001-186">String</span></span>|
|<span data-ttu-id="33001-187">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="33001-187">COLUMN_DEF</span></span>|<span data-ttu-id="33001-188">String</span><span class="sxs-lookup"><span data-stu-id="33001-188">String</span></span>|
|<span data-ttu-id="33001-189">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-189">SQL_DATA_TYPE</span></span>|<span data-ttu-id="33001-190">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-190">Int16</span></span>|
|<span data-ttu-id="33001-191">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="33001-191">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="33001-192">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-192">Int16</span></span>|
|<span data-ttu-id="33001-193">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-193">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="33001-194">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-194">Int32</span></span>|
|<span data-ttu-id="33001-195">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-195">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-196">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-196">Int32</span></span>|
|<span data-ttu-id="33001-197">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-197">IS_NULLABLE</span></span>|<span data-ttu-id="33001-198">String</span><span class="sxs-lookup"><span data-stu-id="33001-198">String</span></span>|
|<span data-ttu-id="33001-199">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33001-199">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="33001-200">String</span><span class="sxs-lookup"><span data-stu-id="33001-200">String</span></span>|
|<span data-ttu-id="33001-201">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33001-201">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="33001-202">String</span><span class="sxs-lookup"><span data-stu-id="33001-202">String</span></span>|
|<span data-ttu-id="33001-203">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-203">SS_DATA_TYPE</span></span>|<span data-ttu-id="33001-204">Byte</span><span class="sxs-lookup"><span data-stu-id="33001-204">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="33001-205">프로시저</span><span class="sxs-lookup"><span data-stu-id="33001-205">Procedures</span></span>

|<span data-ttu-id="33001-206">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-206">ColumnName</span></span>|<span data-ttu-id="33001-207">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-207">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-208">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="33001-208">PROCEDURE_CAT</span></span>|<span data-ttu-id="33001-209">String</span><span class="sxs-lookup"><span data-stu-id="33001-209">String</span></span>|
|<span data-ttu-id="33001-210">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="33001-210">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="33001-211">String</span><span class="sxs-lookup"><span data-stu-id="33001-211">String</span></span>|
|<span data-ttu-id="33001-212">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-212">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-213">String</span><span class="sxs-lookup"><span data-stu-id="33001-213">String</span></span>|
|<span data-ttu-id="33001-214">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="33001-214">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="33001-215">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-215">Int32</span></span>|
|<span data-ttu-id="33001-216">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="33001-216">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="33001-217">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-217">Int32</span></span>|
|<span data-ttu-id="33001-218">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="33001-218">NUM_RESULT_SETS</span></span>|<span data-ttu-id="33001-219">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-219">Int32</span></span>|
|<span data-ttu-id="33001-220">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-220">REMARKS</span></span>|<span data-ttu-id="33001-221">String</span><span class="sxs-lookup"><span data-stu-id="33001-221">String</span></span>|
|<span data-ttu-id="33001-222">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-222">PROCEDURE_TYPE</span></span>|<span data-ttu-id="33001-223">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-223">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="33001-224">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33001-224">ProcedureColumns</span></span>

|<span data-ttu-id="33001-225">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-225">ColumnName</span></span>|<span data-ttu-id="33001-226">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-226">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-227">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="33001-227">PROCEDURE_CAT</span></span>|<span data-ttu-id="33001-228">String</span><span class="sxs-lookup"><span data-stu-id="33001-228">String</span></span>|
|<span data-ttu-id="33001-229">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="33001-229">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="33001-230">String</span><span class="sxs-lookup"><span data-stu-id="33001-230">String</span></span>|
|<span data-ttu-id="33001-231">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-231">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-232">String</span><span class="sxs-lookup"><span data-stu-id="33001-232">String</span></span>|
|<span data-ttu-id="33001-233">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-233">COLUMN_NAME</span></span>|<span data-ttu-id="33001-234">String</span><span class="sxs-lookup"><span data-stu-id="33001-234">String</span></span>|
|<span data-ttu-id="33001-235">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-235">COLUMN_TYPE</span></span>|<span data-ttu-id="33001-236">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-236">Int16</span></span>|
|<span data-ttu-id="33001-237">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-237">DATA_TYPE</span></span>|<span data-ttu-id="33001-238">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-238">Int16</span></span>|
|<span data-ttu-id="33001-239">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-239">TYPE_NAME</span></span>|<span data-ttu-id="33001-240">String</span><span class="sxs-lookup"><span data-stu-id="33001-240">String</span></span>|
|<span data-ttu-id="33001-241">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="33001-241">COLUMN_SIZE</span></span>|<span data-ttu-id="33001-242">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-242">Int32</span></span>|
|<span data-ttu-id="33001-243">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-243">BUFFER_LENGTH</span></span>|<span data-ttu-id="33001-244">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-244">Int32</span></span>|
|<span data-ttu-id="33001-245">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="33001-245">DECIMAL_DIGITS</span></span>|<span data-ttu-id="33001-246">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-246">Int16</span></span>|
|<span data-ttu-id="33001-247">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-247">NUM_PREC_RADIX</span></span>|<span data-ttu-id="33001-248">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-248">Int16</span></span>|
|<span data-ttu-id="33001-249">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-249">NULLABLE</span></span>|<span data-ttu-id="33001-250">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-250">Int16</span></span>|
|<span data-ttu-id="33001-251">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-251">REMARKS</span></span>|<span data-ttu-id="33001-252">String</span><span class="sxs-lookup"><span data-stu-id="33001-252">String</span></span>|
|<span data-ttu-id="33001-253">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="33001-253">COLUMN_DEF</span></span>|<span data-ttu-id="33001-254">String</span><span class="sxs-lookup"><span data-stu-id="33001-254">String</span></span>|
|<span data-ttu-id="33001-255">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-255">SQL_DATA_TYPE</span></span>|<span data-ttu-id="33001-256">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-256">Int16</span></span>|
|<span data-ttu-id="33001-257">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="33001-257">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="33001-258">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-258">Int16</span></span>|
|<span data-ttu-id="33001-259">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-259">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="33001-260">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-260">Int32</span></span>|
|<span data-ttu-id="33001-261">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-261">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-262">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-262">Int32</span></span>|
|<span data-ttu-id="33001-263">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-263">IS_NULLABLE</span></span>|<span data-ttu-id="33001-264">String</span><span class="sxs-lookup"><span data-stu-id="33001-264">String</span></span>|
|<span data-ttu-id="33001-265">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33001-265">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="33001-266">String</span><span class="sxs-lookup"><span data-stu-id="33001-266">String</span></span>|
|<span data-ttu-id="33001-267">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33001-267">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="33001-268">String</span><span class="sxs-lookup"><span data-stu-id="33001-268">String</span></span>|
|<span data-ttu-id="33001-269">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-269">SS_DATA_TYPE</span></span>|<span data-ttu-id="33001-270">Byte</span><span class="sxs-lookup"><span data-stu-id="33001-270">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="33001-271">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33001-271">ProcedureParameters</span></span>

|<span data-ttu-id="33001-272">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-272">ColumnName</span></span>|<span data-ttu-id="33001-273">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-273">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-274">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="33001-274">PROCEDURE_CAT</span></span>|<span data-ttu-id="33001-275">String</span><span class="sxs-lookup"><span data-stu-id="33001-275">String</span></span>|
|<span data-ttu-id="33001-276">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="33001-276">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="33001-277">String</span><span class="sxs-lookup"><span data-stu-id="33001-277">String</span></span>|
|<span data-ttu-id="33001-278">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-278">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-279">String</span><span class="sxs-lookup"><span data-stu-id="33001-279">String</span></span>|
|<span data-ttu-id="33001-280">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-280">COLUMN_NAME</span></span>|<span data-ttu-id="33001-281">String</span><span class="sxs-lookup"><span data-stu-id="33001-281">String</span></span>|
|<span data-ttu-id="33001-282">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-282">COLUMN_TYPE</span></span>|<span data-ttu-id="33001-283">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-283">Int16</span></span>|
|<span data-ttu-id="33001-284">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-284">DATA_TYPE</span></span>|<span data-ttu-id="33001-285">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-285">Int16</span></span>|
|<span data-ttu-id="33001-286">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-286">TYPE_NAME</span></span>|<span data-ttu-id="33001-287">String</span><span class="sxs-lookup"><span data-stu-id="33001-287">String</span></span>|
|<span data-ttu-id="33001-288">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="33001-288">COLUMN_SIZE</span></span>|<span data-ttu-id="33001-289">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-289">Int32</span></span>|
|<span data-ttu-id="33001-290">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-290">BUFFER_LENGTH</span></span>|<span data-ttu-id="33001-291">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-291">Int32</span></span>|
|<span data-ttu-id="33001-292">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="33001-292">DECIMAL_DIGITS</span></span>|<span data-ttu-id="33001-293">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-293">Int16</span></span>|
|<span data-ttu-id="33001-294">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-294">NUM_PREC_RADIX</span></span>|<span data-ttu-id="33001-295">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-295">Int16</span></span>|
|<span data-ttu-id="33001-296">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-296">NULLABLE</span></span>|<span data-ttu-id="33001-297">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-297">Int16</span></span>|
|<span data-ttu-id="33001-298">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-298">REMARKS</span></span>|<span data-ttu-id="33001-299">String</span><span class="sxs-lookup"><span data-stu-id="33001-299">String</span></span>|
|<span data-ttu-id="33001-300">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="33001-300">COLUMN_DEF</span></span>|<span data-ttu-id="33001-301">String</span><span class="sxs-lookup"><span data-stu-id="33001-301">String</span></span>|
|<span data-ttu-id="33001-302">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-302">SQL_DATA_TYPE</span></span>|<span data-ttu-id="33001-303">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-303">Int16</span></span>|
|<span data-ttu-id="33001-304">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="33001-304">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="33001-305">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-305">Int16</span></span>|
|<span data-ttu-id="33001-306">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-306">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="33001-307">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-307">Int32</span></span>|
|<span data-ttu-id="33001-308">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-308">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-309">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-309">Int32</span></span>|
|<span data-ttu-id="33001-310">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-310">IS_NULLABLE</span></span>|<span data-ttu-id="33001-311">String</span><span class="sxs-lookup"><span data-stu-id="33001-311">String</span></span>|
|<span data-ttu-id="33001-312">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33001-312">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="33001-313">String</span><span class="sxs-lookup"><span data-stu-id="33001-313">String</span></span>|
|<span data-ttu-id="33001-314">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33001-314">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="33001-315">String</span><span class="sxs-lookup"><span data-stu-id="33001-315">String</span></span>|
|<span data-ttu-id="33001-316">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-316">SS_DATA_TYPE</span></span>|<span data-ttu-id="33001-317">Byte</span><span class="sxs-lookup"><span data-stu-id="33001-317">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="33001-318">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="33001-318">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="33001-319">Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33001-319">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="33001-320">테이블</span><span class="sxs-lookup"><span data-stu-id="33001-320">Tables</span></span>

- <span data-ttu-id="33001-321">열</span><span class="sxs-lookup"><span data-stu-id="33001-321">Columns</span></span>

- <span data-ttu-id="33001-322">프로시저</span><span class="sxs-lookup"><span data-stu-id="33001-322">Procedures</span></span>

- <span data-ttu-id="33001-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33001-323">ProcedureColumns</span></span>

- <span data-ttu-id="33001-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33001-324">ProcedureParameters</span></span>

- <span data-ttu-id="33001-325">보기</span><span class="sxs-lookup"><span data-stu-id="33001-325">Views</span></span>

- <span data-ttu-id="33001-326">인덱스</span><span class="sxs-lookup"><span data-stu-id="33001-326">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="33001-327">테이블 및 뷰</span><span class="sxs-lookup"><span data-stu-id="33001-327">Tables and Views</span></span>

|<span data-ttu-id="33001-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-328">ColumnName</span></span>|<span data-ttu-id="33001-329">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-329">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-330">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-330">TABLE_QUALIFIER</span></span>|<span data-ttu-id="33001-331">String</span><span class="sxs-lookup"><span data-stu-id="33001-331">String</span></span>|
|<span data-ttu-id="33001-332">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-332">TABLE_OWNER</span></span>|<span data-ttu-id="33001-333">String</span><span class="sxs-lookup"><span data-stu-id="33001-333">String</span></span>|
|<span data-ttu-id="33001-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-334">TABLE_NAME</span></span>|<span data-ttu-id="33001-335">String</span><span class="sxs-lookup"><span data-stu-id="33001-335">String</span></span>|
|<span data-ttu-id="33001-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-336">TABLE_TYPE</span></span>|<span data-ttu-id="33001-337">String</span><span class="sxs-lookup"><span data-stu-id="33001-337">String</span></span>|
|<span data-ttu-id="33001-338">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-338">REMARKS</span></span>|<span data-ttu-id="33001-339">String</span><span class="sxs-lookup"><span data-stu-id="33001-339">String</span></span>|

### <a name="columns"></a><span data-ttu-id="33001-340">열</span><span class="sxs-lookup"><span data-stu-id="33001-340">Columns</span></span>

|<span data-ttu-id="33001-341">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-341">ColumnName</span></span>|<span data-ttu-id="33001-342">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-342">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-343">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-343">TABLE_QUALIFIER</span></span>|<span data-ttu-id="33001-344">String</span><span class="sxs-lookup"><span data-stu-id="33001-344">String</span></span>|
|<span data-ttu-id="33001-345">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-345">TABLE_OWNER</span></span>|<span data-ttu-id="33001-346">String</span><span class="sxs-lookup"><span data-stu-id="33001-346">String</span></span>|
|<span data-ttu-id="33001-347">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-347">TABLE_NAME</span></span>|<span data-ttu-id="33001-348">String</span><span class="sxs-lookup"><span data-stu-id="33001-348">String</span></span>|
|<span data-ttu-id="33001-349">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-349">COLUMN_NAME</span></span>|<span data-ttu-id="33001-350">String</span><span class="sxs-lookup"><span data-stu-id="33001-350">String</span></span>|
|<span data-ttu-id="33001-351">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-351">DATA_TYPE</span></span>|<span data-ttu-id="33001-352">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-352">Int16</span></span>|
|<span data-ttu-id="33001-353">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-353">TYPE_NAME</span></span>|<span data-ttu-id="33001-354">String</span><span class="sxs-lookup"><span data-stu-id="33001-354">String</span></span>|
|<span data-ttu-id="33001-355">PRECISION</span><span class="sxs-lookup"><span data-stu-id="33001-355">PRECISION</span></span>|<span data-ttu-id="33001-356">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-356">Int32</span></span>|
|<span data-ttu-id="33001-357">LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-357">LENGTH</span></span>|<span data-ttu-id="33001-358">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-358">Int32</span></span>|
|<span data-ttu-id="33001-359">SCALE</span><span class="sxs-lookup"><span data-stu-id="33001-359">SCALE</span></span>|<span data-ttu-id="33001-360">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-360">Int16</span></span>|
|<span data-ttu-id="33001-361">RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-361">RADIX</span></span>|<span data-ttu-id="33001-362">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-362">Int16</span></span>|
|<span data-ttu-id="33001-363">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-363">NULLABLE</span></span>|<span data-ttu-id="33001-364">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-364">Int16</span></span>|
|<span data-ttu-id="33001-365">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-365">REMARKS</span></span>|<span data-ttu-id="33001-366">String</span><span class="sxs-lookup"><span data-stu-id="33001-366">String</span></span>|
|<span data-ttu-id="33001-367">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-367">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-368">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-368">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="33001-369">프로시저</span><span class="sxs-lookup"><span data-stu-id="33001-369">Procedures</span></span>

|<span data-ttu-id="33001-370">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-370">ColumnName</span></span>|<span data-ttu-id="33001-371">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-371">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-372">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-372">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="33001-373">String</span><span class="sxs-lookup"><span data-stu-id="33001-373">String</span></span>|
|<span data-ttu-id="33001-374">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-374">PROCEDURE_OWNER</span></span>|<span data-ttu-id="33001-375">String</span><span class="sxs-lookup"><span data-stu-id="33001-375">String</span></span>|
|<span data-ttu-id="33001-376">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-376">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-377">String</span><span class="sxs-lookup"><span data-stu-id="33001-377">String</span></span>|
|<span data-ttu-id="33001-378">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="33001-378">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="33001-379">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-379">Int16</span></span>|
|<span data-ttu-id="33001-380">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="33001-380">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="33001-381">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-381">Int16</span></span>|
|<span data-ttu-id="33001-382">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="33001-382">NUM_RESULT_SETS</span></span>|<span data-ttu-id="33001-383">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-383">Int16</span></span>|
|<span data-ttu-id="33001-384">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-384">REMARKS</span></span>|<span data-ttu-id="33001-385">String</span><span class="sxs-lookup"><span data-stu-id="33001-385">String</span></span>|
|<span data-ttu-id="33001-386">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-386">PROCEDURE_TYPE</span></span>|<span data-ttu-id="33001-387">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-387">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="33001-388">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33001-388">ProcedureColumns</span></span>

|<span data-ttu-id="33001-389">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-389">ColumnName</span></span>|<span data-ttu-id="33001-390">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-390">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-391">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-391">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="33001-392">String</span><span class="sxs-lookup"><span data-stu-id="33001-392">String</span></span>|
|<span data-ttu-id="33001-393">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-393">PROCEDURE_OWNER</span></span>|<span data-ttu-id="33001-394">String</span><span class="sxs-lookup"><span data-stu-id="33001-394">String</span></span>|
|<span data-ttu-id="33001-395">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-395">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-396">String</span><span class="sxs-lookup"><span data-stu-id="33001-396">String</span></span>|
|<span data-ttu-id="33001-397">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-397">COLUMN_NAME</span></span>|<span data-ttu-id="33001-398">String</span><span class="sxs-lookup"><span data-stu-id="33001-398">String</span></span>|
|<span data-ttu-id="33001-399">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-399">COLUMN_TYPE</span></span>|<span data-ttu-id="33001-400">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-400">Int16</span></span>|
|<span data-ttu-id="33001-401">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-401">DATA_TYPE</span></span>|<span data-ttu-id="33001-402">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-402">Int16</span></span>|
|<span data-ttu-id="33001-403">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-403">TYPE_NAME</span></span>|<span data-ttu-id="33001-404">String</span><span class="sxs-lookup"><span data-stu-id="33001-404">String</span></span>|
|<span data-ttu-id="33001-405">PRECISION</span><span class="sxs-lookup"><span data-stu-id="33001-405">PRECISION</span></span>|<span data-ttu-id="33001-406">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-406">Int32</span></span>|
|<span data-ttu-id="33001-407">LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-407">LENGTH</span></span>|<span data-ttu-id="33001-408">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-408">Int32</span></span>|
|<span data-ttu-id="33001-409">SCALE</span><span class="sxs-lookup"><span data-stu-id="33001-409">SCALE</span></span>|<span data-ttu-id="33001-410">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-410">Int16</span></span>|
|<span data-ttu-id="33001-411">RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-411">RADIX</span></span>|<span data-ttu-id="33001-412">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-412">Int16</span></span>|
|<span data-ttu-id="33001-413">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-413">NULLABLE</span></span>|<span data-ttu-id="33001-414">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-414">Int16</span></span>|
|<span data-ttu-id="33001-415">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-415">REMARKS</span></span>|<span data-ttu-id="33001-416">String</span><span class="sxs-lookup"><span data-stu-id="33001-416">String</span></span>|
|<span data-ttu-id="33001-417">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="33001-417">OVERLOAD</span></span>|<span data-ttu-id="33001-418">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-418">Int32</span></span>|
|<span data-ttu-id="33001-419">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-419">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-420">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-420">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="33001-421">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="33001-421">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="33001-422">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="33001-422">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="33001-423">테이블</span><span class="sxs-lookup"><span data-stu-id="33001-423">Tables</span></span>

- <span data-ttu-id="33001-424">인덱스</span><span class="sxs-lookup"><span data-stu-id="33001-424">Indexes</span></span>

- <span data-ttu-id="33001-425">열</span><span class="sxs-lookup"><span data-stu-id="33001-425">Columns</span></span>

- <span data-ttu-id="33001-426">프로시저</span><span class="sxs-lookup"><span data-stu-id="33001-426">Procedures</span></span>

- <span data-ttu-id="33001-427">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33001-427">ProcedureColumns</span></span>

- <span data-ttu-id="33001-428">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33001-428">ProcedureParameters</span></span>

- <span data-ttu-id="33001-429">보기</span><span class="sxs-lookup"><span data-stu-id="33001-429">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="33001-430">테이블 및 뷰</span><span class="sxs-lookup"><span data-stu-id="33001-430">Tables and Views</span></span>

|<span data-ttu-id="33001-431">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-431">ColumnName</span></span>|<span data-ttu-id="33001-432">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-432">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-433">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-433">TABLE_QUALIFIER</span></span>|<span data-ttu-id="33001-434">String</span><span class="sxs-lookup"><span data-stu-id="33001-434">String</span></span>|
|<span data-ttu-id="33001-435">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-435">TABLE_OWNER</span></span>|<span data-ttu-id="33001-436">String</span><span class="sxs-lookup"><span data-stu-id="33001-436">String</span></span>|
|<span data-ttu-id="33001-437">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-437">TABLE_NAME</span></span>|<span data-ttu-id="33001-438">String</span><span class="sxs-lookup"><span data-stu-id="33001-438">String</span></span>|
|<span data-ttu-id="33001-439">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-439">TABLE_TYPE</span></span>|<span data-ttu-id="33001-440">String</span><span class="sxs-lookup"><span data-stu-id="33001-440">String</span></span>|
|<span data-ttu-id="33001-441">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-441">REMARKS</span></span>|<span data-ttu-id="33001-442">String</span><span class="sxs-lookup"><span data-stu-id="33001-442">String</span></span>|

### <a name="columns"></a><span data-ttu-id="33001-443">열</span><span class="sxs-lookup"><span data-stu-id="33001-443">Columns</span></span>

|<span data-ttu-id="33001-444">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-444">ColumnName</span></span>|<span data-ttu-id="33001-445">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-445">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-446">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-446">TABLE_QUALIFIER</span></span>|<span data-ttu-id="33001-447">String</span><span class="sxs-lookup"><span data-stu-id="33001-447">String</span></span>|
|<span data-ttu-id="33001-448">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-448">TABLE_OWNER</span></span>|<span data-ttu-id="33001-449">String</span><span class="sxs-lookup"><span data-stu-id="33001-449">String</span></span>|
|<span data-ttu-id="33001-450">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-450">TABLE_NAME</span></span>|<span data-ttu-id="33001-451">String</span><span class="sxs-lookup"><span data-stu-id="33001-451">String</span></span>|
|<span data-ttu-id="33001-452">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-452">COLUMN_NAME</span></span>|<span data-ttu-id="33001-453">String</span><span class="sxs-lookup"><span data-stu-id="33001-453">String</span></span>|
|<span data-ttu-id="33001-454">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-454">DATA_TYPE</span></span>|<span data-ttu-id="33001-455">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-455">Int16</span></span>|
|<span data-ttu-id="33001-456">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-456">TYPE_NAME</span></span>|<span data-ttu-id="33001-457">String</span><span class="sxs-lookup"><span data-stu-id="33001-457">String</span></span>|
|<span data-ttu-id="33001-458">PRECISION</span><span class="sxs-lookup"><span data-stu-id="33001-458">PRECISION</span></span>|<span data-ttu-id="33001-459">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-459">Int32</span></span>|
|<span data-ttu-id="33001-460">LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-460">LENGTH</span></span>|<span data-ttu-id="33001-461">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-461">Int32</span></span>|
|<span data-ttu-id="33001-462">SCALE</span><span class="sxs-lookup"><span data-stu-id="33001-462">SCALE</span></span>|<span data-ttu-id="33001-463">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-463">Int16</span></span>|
|<span data-ttu-id="33001-464">RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-464">RADIX</span></span>|<span data-ttu-id="33001-465">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-465">Int16</span></span>|
|<span data-ttu-id="33001-466">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-466">NULLABLE</span></span>|<span data-ttu-id="33001-467">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-467">Int16</span></span>|
|<span data-ttu-id="33001-468">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-468">REMARKS</span></span>|<span data-ttu-id="33001-469">String</span><span class="sxs-lookup"><span data-stu-id="33001-469">String</span></span>|
|<span data-ttu-id="33001-470">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-470">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-471">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-471">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="33001-472">프로시저</span><span class="sxs-lookup"><span data-stu-id="33001-472">Procedures</span></span>

|<span data-ttu-id="33001-473">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-473">ColumnName</span></span>|<span data-ttu-id="33001-474">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-474">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-475">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-475">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="33001-476">String</span><span class="sxs-lookup"><span data-stu-id="33001-476">String</span></span>|
|<span data-ttu-id="33001-477">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-477">PROCEDURE_OWNER</span></span>|<span data-ttu-id="33001-478">String</span><span class="sxs-lookup"><span data-stu-id="33001-478">String</span></span>|
|<span data-ttu-id="33001-479">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-479">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-480">String</span><span class="sxs-lookup"><span data-stu-id="33001-480">String</span></span>|
|<span data-ttu-id="33001-481">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="33001-481">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="33001-482">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-482">Int16</span></span>|
|<span data-ttu-id="33001-483">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="33001-483">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="33001-484">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-484">Int16</span></span>|
|<span data-ttu-id="33001-485">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="33001-485">NUM_RESULT_SETS</span></span>|<span data-ttu-id="33001-486">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-486">Int16</span></span>|
|<span data-ttu-id="33001-487">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-487">REMARKS</span></span>|<span data-ttu-id="33001-488">String</span><span class="sxs-lookup"><span data-stu-id="33001-488">String</span></span>|
|<span data-ttu-id="33001-489">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-489">PROCEDURE_TYPE</span></span>|<span data-ttu-id="33001-490">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-490">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="33001-491">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33001-491">ProcedureColumns</span></span>

|<span data-ttu-id="33001-492">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-492">ColumnName</span></span>|<span data-ttu-id="33001-493">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-493">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-494">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="33001-494">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="33001-495">String</span><span class="sxs-lookup"><span data-stu-id="33001-495">String</span></span>|
|<span data-ttu-id="33001-496">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="33001-496">PROCEDURE_OWNER</span></span>|<span data-ttu-id="33001-497">String</span><span class="sxs-lookup"><span data-stu-id="33001-497">String</span></span>|
|<span data-ttu-id="33001-498">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-498">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-499">String</span><span class="sxs-lookup"><span data-stu-id="33001-499">String</span></span>|
|<span data-ttu-id="33001-500">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-500">COLUMN_NAME</span></span>|<span data-ttu-id="33001-501">String</span><span class="sxs-lookup"><span data-stu-id="33001-501">String</span></span>|
|<span data-ttu-id="33001-502">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-502">COLUMN_TYPE</span></span>|<span data-ttu-id="33001-503">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-503">Int16</span></span>|
|<span data-ttu-id="33001-504">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-504">DATA_TYPE</span></span>|<span data-ttu-id="33001-505">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-505">Int16</span></span>|
|<span data-ttu-id="33001-506">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-506">TYPE_NAME</span></span>|<span data-ttu-id="33001-507">String</span><span class="sxs-lookup"><span data-stu-id="33001-507">String</span></span>|
|<span data-ttu-id="33001-508">PRECISION</span><span class="sxs-lookup"><span data-stu-id="33001-508">PRECISION</span></span>|<span data-ttu-id="33001-509">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-509">Int32</span></span>|
|<span data-ttu-id="33001-510">LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-510">LENGTH</span></span>|<span data-ttu-id="33001-511">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-511">Int32</span></span>|
|<span data-ttu-id="33001-512">SCALE</span><span class="sxs-lookup"><span data-stu-id="33001-512">SCALE</span></span>|<span data-ttu-id="33001-513">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-513">Int16</span></span>|
|<span data-ttu-id="33001-514">RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-514">RADIX</span></span>|<span data-ttu-id="33001-515">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-515">Int16</span></span>|
|<span data-ttu-id="33001-516">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-516">NULLABLE</span></span>|<span data-ttu-id="33001-517">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-517">Int16</span></span>|
|<span data-ttu-id="33001-518">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-518">REMARKS</span></span>|<span data-ttu-id="33001-519">String</span><span class="sxs-lookup"><span data-stu-id="33001-519">String</span></span>|
|<span data-ttu-id="33001-520">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="33001-520">OVERLOAD</span></span>|<span data-ttu-id="33001-521">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-521">Int32</span></span>|
|<span data-ttu-id="33001-522">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-522">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-523">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-523">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="33001-524">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33001-524">ProcedureParameters</span></span>

|<span data-ttu-id="33001-525">ColumnName</span><span class="sxs-lookup"><span data-stu-id="33001-525">ColumnName</span></span>|<span data-ttu-id="33001-526">DataType</span><span class="sxs-lookup"><span data-stu-id="33001-526">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="33001-527">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="33001-527">PROCEDURE_CAT</span></span>|<span data-ttu-id="33001-528">String</span><span class="sxs-lookup"><span data-stu-id="33001-528">String</span></span>|
|<span data-ttu-id="33001-529">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="33001-529">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="33001-530">String</span><span class="sxs-lookup"><span data-stu-id="33001-530">String</span></span>|
|<span data-ttu-id="33001-531">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-531">PROCEDURE_NAME</span></span>|<span data-ttu-id="33001-532">String</span><span class="sxs-lookup"><span data-stu-id="33001-532">String</span></span>|
|<span data-ttu-id="33001-533">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-533">COLUMN_NAME</span></span>|<span data-ttu-id="33001-534">String</span><span class="sxs-lookup"><span data-stu-id="33001-534">String</span></span>|
|<span data-ttu-id="33001-535">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-535">COLUMN_TYPE</span></span>|<span data-ttu-id="33001-536">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-536">Int16</span></span>|
|<span data-ttu-id="33001-537">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-537">DATA_TYPE</span></span>|<span data-ttu-id="33001-538">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-538">Int16</span></span>|
|<span data-ttu-id="33001-539">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33001-539">TYPE_NAME</span></span>|<span data-ttu-id="33001-540">String</span><span class="sxs-lookup"><span data-stu-id="33001-540">String</span></span>|
|<span data-ttu-id="33001-541">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="33001-541">COLUMN_SIZE</span></span>|<span data-ttu-id="33001-542">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-542">Int32</span></span>|
|<span data-ttu-id="33001-543">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-543">BUFFER_LENGTH</span></span>|<span data-ttu-id="33001-544">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-544">Int32</span></span>|
|<span data-ttu-id="33001-545">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="33001-545">DECIMAL_DIGITS</span></span>|<span data-ttu-id="33001-546">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-546">Int16</span></span>|
|<span data-ttu-id="33001-547">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="33001-547">NUM_PREC_RADIX</span></span>|<span data-ttu-id="33001-548">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-548">Int16</span></span>|
|<span data-ttu-id="33001-549">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-549">NULLABLE</span></span>|<span data-ttu-id="33001-550">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-550">Int16</span></span>|
|<span data-ttu-id="33001-551">REMARKS</span><span class="sxs-lookup"><span data-stu-id="33001-551">REMARKS</span></span>|<span data-ttu-id="33001-552">String</span><span class="sxs-lookup"><span data-stu-id="33001-552">String</span></span>|
|<span data-ttu-id="33001-553">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="33001-553">COLUMN_DEF</span></span>|<span data-ttu-id="33001-554">String</span><span class="sxs-lookup"><span data-stu-id="33001-554">String</span></span>|
|<span data-ttu-id="33001-555">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33001-555">SQL_DATA_TYPE</span></span>|<span data-ttu-id="33001-556">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-556">Int16</span></span>|
|<span data-ttu-id="33001-557">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="33001-557">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="33001-558">Int16</span><span class="sxs-lookup"><span data-stu-id="33001-558">Int16</span></span>|
|<span data-ttu-id="33001-559">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33001-559">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="33001-560">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-560">Int32</span></span>|
|<span data-ttu-id="33001-561">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33001-561">ORDINAL_POSITION</span></span>|<span data-ttu-id="33001-562">Int32</span><span class="sxs-lookup"><span data-stu-id="33001-562">Int32</span></span>|
|<span data-ttu-id="33001-563">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33001-563">IS_NULLABLE</span></span>|<span data-ttu-id="33001-564">String</span><span class="sxs-lookup"><span data-stu-id="33001-564">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="33001-565">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33001-565">See also</span></span>

- [<span data-ttu-id="33001-566">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="33001-566">ADO.NET Overview</span></span>](ado-net-overview.md)
