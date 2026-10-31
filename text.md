mysql -u qyotupjl_shopotronicsuser -p qyotupjl_dbshopotronics -e "ALTER DATABASE qyotupjl_dbshopotronics CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;"


mysql -u qyotupjl_shopotronicsuser -p qyotupjl_dbshopotronics -e "
SELECT CONCAT('ALTER TABLE \`', TABLE_NAME, '\` CONVERT TO CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;')
FROM information_schema.TABLES WHERE TABLE_SCHEMA = 'qyotupjl_dbshopotronics';
" > convert_charset.sql


mysql -u qyotupjl_shopotronicsuser -p qyotupjl_dbshopotronics < convert_charset.sql