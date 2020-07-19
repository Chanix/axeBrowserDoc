# \_\_AXE\_\_.fsys
文件系统相关的扩展功能

---

	canRead = function(filename) {
	canWrite = function(filename) {
	canReadWrite = function(filename) {
	exists = function(filename) {
   	isDir = function(filename) {
	isFile = function(filename) {
	isHidden = function(filename) {
	isReadonly = function(filename) {
	isSystemFile = function(filename) {
	fullpath = function(filename) {
	listFiles= function(dir, wildcard, recursive) {
	readFileToString = function(filename) {
	readFile = readFileToString;
	writeStringToFile = function(filename, content, ifAppend = false) {
	writeFile = writeStringToFile;