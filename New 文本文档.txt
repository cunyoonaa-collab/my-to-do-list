const input = document.getElementById("taskInput");
const button = document.getElementById("addButton");
const list = document.getElementById("taskList");

button.addEventListener("click", function() {

    const task = input.value;

    if (task !== "") {

        const item = document.createElement("li");

        const checkbox = document.createElement("input");
        checkbox.type = "checkbox";

        checkbox.addEventListener("change", function() {
            if (checkbox.checked) {
                item.style.textDecoration = "line-through";
            } else {
                item.style.textDecoration = "none";
            }
        });

        item.appendChild(checkbox);
        item.appendChild(document.createTextNode(" " + task));

        list.appendChild(item);

        input.value = "";
    }

});